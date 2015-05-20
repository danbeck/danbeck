---
layout: post
title:  "MySQL: Creating a user and granting rights"
date:   2010-07-09 09:03:00
categories: MySQL
---
<h2>Overview</h2>
Lists are predefined widgets that mostly look like their native counterparts. 

<h2>Markup declaration</h2>
A container is declared as a list by setting the attribute <code>data-role="list"</code>. Lists consist of an <ul> element, containing <li> elements (i.e. list items). 

The following code declares a list consisting of two list items:

```html
<section data-role="list">
  <ul>
    <li>
      <p>Label</p>
    </li>
    <li>
      <p>Label</p>
      <p>Secondary Label</p>
    </li>
  </ul>
</section>  
```

List can contain <header>-elements.

```html
<section data-role="list">
  <header>Header</header>
  <ul>
    <li>
      <p>Label</p>
    </li>
  </ul>
</section>  
```

Here is a screenshot of a header element and a "normal" list element:
[caption id="attachment_844" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/HeaderWithListItem.png"><img src="http://daniel-beck.org/wp-content/uploads/HeaderWithListItem.png" alt="A list made of a header and a normal list item" width="302" height="92" class="size-full wp-image-844" /></a> A list with a header element[/caption]


To give the user the illusion of "progression", list items can be designed to have an arrow on the right side. This is realized by surrounding a list-item with an <a>-element:

```html
<section data-role="list">
  <header>Header</header>
  <ul>
    <li>
      <a href="#">
        <p>Open this item</p>
      </a>
    </li>
  </ul>
</section>  
```

[caption id="attachment_846" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/ListProgression.png"><img src="http://daniel-beck.org/wp-content/uploads/ListProgression.png" alt="List with a progression item" width="302" height="88" class="size-full wp-image-846" /></a> List with a progression item[/caption]

List items can have an icon on the left side:

```html
<section data-role="list">
  <header>Header</header>
  <ul>
    <li>
      <a>
        <aside>
          <img src="avatar_contacts_list@8.png">
        </aside>
        <p>Label</p>
      </a>
    </li>
  </ul>
</section>
```

[caption id="attachment_847" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/LabelListItem.png"><img src="http://daniel-beck.org/wp-content/uploads/LabelListItem.png" alt="List item with a label" width="302" height="65" class="size-full wp-image-847" /></a> List item with a label[/caption]

Lists can also contain other elements like text inputs, switches and checkboxes:

```html
<section data-role="list">
  <ul>
    <li>
      <p>Switch</p>
      <label>
        <input type="checkbox" checked="" data-type="switch">
          <span class="toggle">
            <span class="toggle-handle"></span>
            <span class="toggle-bg"></span>
          </span>
      </label>
     </li>
    <li>
      <p>Checkbox</p>
      <label>
        <input type="checkbox">
        <span></span>
      </label>
    </li>
  </ul>
</section>
```

[caption id="attachment_849" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/CheckboxAndSwithMenuItems.png"><img src="http://daniel-beck.org/wp-content/uploads/CheckboxAndSwithMenuItems.png" alt="Checkbox and switch menu items" width="302" height="117" class="size-full wp-image-849" /></a> Checkbox and switch menu items[/caption]


<h2>Javascript access method</h2>
Accessing the list widget is made as follows:

```javascript
var UI = new UbuntuUI();
UI.init();
var list= UI.list("#id"); // a selector is passed as argument
```

<h2>Interface definition</h2>

```javascript
interface List{
  void setHeader(DOMString text);
  void append(DOMSting text, DOMString label, DOMString id, AsyncOperationCallback onClick, Object user_data);
  Element at(unsigned long index);
  void remove(unsigned long index);
  void removeAllItems();
  void forEach(AsyncOperationCallback func);
};
```


<h2>Method</h2>

<dl>
<dt>void setHeader(DOMString text)</dt>
<dd>replaces a header with a new header labelled with <code>text</code>. If several headers exist, an exception is thrown. If no header exists, nothing happens.
</dd>
<dt>void append(DOMSting text, DOMString label, DOMString id, AsyncOperationCallback onClick, Object user_data)</dt>
<dd>appends a new list element to the list. The only mandatory parameter is <code>text</code>, the other parameters are optional.  <code>text</code> is displayed on the left side of the created list element, <code>label</code> is normally used to show an image or a toggle, it is displayed on the right side. With "id" the list element gets assigned an "id"-attribute. A click event-handler can be passed with <code>onclick</code>. <code>data</code> allows to pass supplementary data to the event-handler. The following example shows how to use the append method:

```javascript
UI.list('somelist').append("The"); 
UI.list('somelist').append("answer"); 
UI.list('somelist').append("is"); 
UI.list('somelist').append("42", "path/to/image.png", "clickMeId", onClick, {num: 42});
```
</dd>

<dt>Element at(unsigned long index)</dt>
<dd>returns the n-th list item of the list, <code>null</code> on failure.</dd>

<dt>void remove(unsigned long index)</dt>
<dd>removes the n-th list item of the list, if it exists. If that element does not exist, nothing happens. List item indexes start at 1.</dd>

<dt>void removeAllItems(unsigned long index)</dt>
<dd>removes all the items from the list.</dd>

<dt>void forEach(AsyncOperationCallback func)</dt>
<dd>iterates over the list items and calls the <code>func</code> function on each item. The <code>func</code> function gets the DOM node and its index.
In the following example, <code>forEach()</code> is used to assign a CSS class named "odd" to each second item:

```javascript
UI.list('list').forEach(function(element, index) {
   if(index % 2 === 1)
      element.classList.add("odd");
});
```
</dd>
</dl>