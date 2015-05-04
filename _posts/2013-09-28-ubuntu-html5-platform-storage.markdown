---
layout: post
title:  "Ubuntu HTML5 platform: Storage"
date:   2013-09-28 22:24:00
categories: Ubuntu HTML5
---
Several options to persist structured data with HTML5 client devices exist:

 * Web Storage (i.e. localstorage)
 * WebSQL
 * IndexedDB

Ubuntu Touch supports all three options. However, the implemented IndexedDB version uses an old API. We will see how to remidy this by using a polyfill.

<h2>Web Storage</h2>
The <a href="http://dev.w3.org/html5/webstorage/">Web Storage W3C specification</a> defines an API to save named key/value pairs. The web storage attribute can be accessed with <code>window.localstorage</code> for persistent data, and with <code>window.sessionstorage</code> for data that ist discarded after the session quits.

Local storage and session storage both have the same API to save key/value pairs. Key and value must both be <code>Strings</code>. Using them is in fact very simple, its API <a href="http://www.w3.org/TR/webstorage/#storage-0">is very small</a>. Here an example that saves an item in the localstorage, retrieves it, and deletes it afterwards:

```javascript
// saves data in the local storage
localStorage.setItem("username", "max");

// retrieves the data  
var retrievedUsername = localStorage.getItem("username");

// removes the data
localStorage.removeItem("username");
```

Since keys and values are <code>Strings</code>, to retrieve <code>integers</code> or <code>floats</code>, functions like <code>parseInt()</code> or <code>parseFloat()</code> must be used. Objects can be stored in the localstorage by storing them as JSON Strings:

```javascript
var someObject = {username="foo", password="1234"};

// saves the data as JSON
localStorage.setItem("userdata", JSON.stringify(someObject));

// retrieves the data as JSON
var retrievedUserData = JSON.parse(localStorage.getItem("userdata"));
```

Localstorage has the huge advantage that it is supported by all the major web browsers (even IE8!). It however has several disadvantages, too, including:
 
 * Only <code>Strings</code> can be saved. There is no query language to retrieve objects.
 * Since localstorage only saves <code>Strings</code>, it scales badly for bigger amount of data. As a matter of fact, most implementations of localstorage throw an exception when more than 5MB are used!</li>
 * It has strange locking behavior, which makes it difficult to use when more than one browser window is open.

Most of these shortcomings are solved by WebSQL and indexedDB.

<h2 name="websql">WebSQL</h2>
The <a href="http://www.w3.org/TR/webdatabase/">Web SQL Database specification</a> isn't maintained anymore and is not part of the HTML5 specification. It is however very important for us, since it is supported by the Ubuntu Touch WebKit implementation! It is also supported by Google Chrome, Safari and Android Browser; IE and Firefox do not implement it.
  
Web SQL introduces a set of APIs to manipulate client-side databases using SQL. The specification is based on SQLite and defines API methods to open databases, create transactions and execute SQL statements:

 * <code>Database window.openDatabase(database_name, version, database_description, estimated__size, creationCallback) </code>: opens a database, or creates it if it does not exist.
 * <code>database.transaction(callbackFunc, errorCallback, successCallback)</code>: opens a transaction. The callback methods are executed in a transaction.
* <code>transaction.executeSql(sqlStatement, parameters, callbackFunc, errorCallback)</code>: executes a SQL statement .

We jump in and show the API in action:

```javascript
var db = window.openDatabase("myDatabase", "1.0", 
  "TestDatabase", 5*1024*1024);
 
if(!db) {
  alert("The DB could not be created");
  return false
}

// Creates a table and inserts some data into it
db.transaction(createAndInitSQLTable);

function createAndInitSQLTable(tx) {
  tx.executeSql('CREATE TABLE 
        IF NOT EXISTS CONFIGURATION(id unique, key TEXT, value TEXT)');
  tx.executeSql('INSERT INTO CONFIGURATION (id, key, value) 
        VALUES (1, "admin", "secret")');
  tx.executeSql('INSERT INTO CONFIGURATION (id, key, value) 
        VALUES (1, "minimize_on_close", "false")');
}

// displays the result in the HTML
db.transaction(function (tx) {  
  tx.executeSql('SELECT * FROM CONFIGURATION ', [], 
      showConfiguration, null);
});


function showConfiguration(tx, results){
  var domElem =  document.getElementById('#configurationEntries');
  var rows = results.rows;
  for (i = 0; i < rows.length; i++){
    var keyValue = rows.item(i).key + ": " + rows.item(i).value;
    domElem.innerHTML +=  keyValue ;
}
```

One disadvantage of WebSQL is that it is not a W3C standard. Mozilla/Firefox even decided to <a href="https://hacks.mozilla.org/2010/06/beyond-html5-database-apis-and-the-road-to-indexeddb/">not endorse</a> it. Instead, IndexedDB is the alternative advocated by Mozilla.

<h2 name="indexeddb">IndexedDB</h2>
Like Web Storage, IndexedDB is a key/value storage. It has many advantages over Web Storage: 

 * Javascript Objects can be saved.
 * Accessing values (which can be objects) can be made fast by creating "indexes".
 * It offers transactions.
 * It is asynchronous, thus it does not block the program flow.
 * It is supported by many browsers: Google Chrome (only the desktop version), Firefox and IE10+.


The bad news is that only an old version of IndexedDB is implemented in Ubuntu Touch (the Android browser implements the same old verison). This version does, for example, not define the <code>IDBVersionChangeEvent</code> variable.
Instead of using this fossil version of the W3C API, I recommand to use a polyfill to enable IndexedDB using WebSql. I use <a href="http://nparashuram.com/IndexedDBShim/">IndexDBShim</a> for that. 

<div class="box">
<h3>Polyfills</h3>
In web development, a polyfill (or polyfiller) is downloadable code which provides facilities that are not built into a web browser. For example, many features of HTML5 are not supported by versions of Internet Explorer older than version 8 or 9, but can be used by web pages if those pages install a polyfill.
</div>

To enable IndexDBShim add this to your HTML page:

```javascript
<script src="IndexedDBShim.js"></script>
```

Then enable the polyfill it as follows:

```javascript
// Is there a current implementation of IndexedDB?
var requireShim = typeof window.IDBVersionChangeEvent === 'undefined';

// Is WebSQL available?
var supportsWebSql = typeof window.openDatabase != 'undefined';

if(requireShim &amp;&amp; supportsWebSql){
  window.shimIndexedDB.__useShim(); // Use the Polyfills 
}
```

Using a polyfill to emulate IndexedDB with WebSQL isn't really a bad thing: for example, Firefox already implements indexedDB with SQL Lite.

Here is a small example which shows how to use indexedDB:

```javascript
var users = [
  { name: "Anne" },
  { name: "Marie" },
  { name: "Thomas" }
];
 
var request = window.indexedDB.open("UserDB", "My user database");
request.onsuccess = function(event) {
  var objectStore = event.result.objectStore("users");
  for (var index = 0; i < kids.length; i++) {
    var user = users[i];
    objectStore.add(user).onsuccess = function(event) {
      document.getElementById("display").textContent +=
            user.name + " with id " + event.result;
    };
  }
};
```

<h2>Conclusion</h2>
Ubuntu Touch offers different HTML5 storing options to save structured data. "Webstorage" is the most easy and the most effective for unstructered and small data. "WebSQL" brings the whole world of SQL to the browser. Finally, "IndexedDB" directly allows to persist Javascript objects.