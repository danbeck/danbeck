---
layout: page
title:  Dialog
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---

<h2>Overview</h2>
Dialogs are modal windows. They disallow any other interaction with the application while waiting on a user interaction.


<h2>Markup declaration</h2>
Dialogs are declared with the attribute <code>data-role="dialog"</code>. They can contain other HTML elements:

```html
<div id="dialog1" style="display: block" data-role="dialog">
  <section>
    <h1>Simple Dialog</h1>
    <p>Are you sure you want to delete this file?</p>
    <menu>
      <button id="no" data-role="button">Cancel</button>
      <button id="yes" class="danger" data-role="button">Delete</button>
    </menu>
  </section>
<div>
```

The following example prompts the user for its name:

```html
<div id="dialog2" style="display: block" data-role="dialog">
  <section>
    <h1>Name Dialog</h1>
    <p>What is you name?</p>
    <menu>
      <input type="text" id="nameField"/>
      <button data-role="button" id="okButton">OK<button>
    </menu>
  </section>
</div>
```

[caption id="attachment_702" align="alignnone" width="371"]<a href="http://daniel-beck.org/wp-content/uploads/dialogTextInput.png"><img src="http://daniel-beck.org/wp-content/uploads/dialogTextInput.png" alt="Prompt Dialog" width="371" height="197" class="size-full wp-image-702" /></a> Prompt Dialog[/caption]


<h2>Javascript Access method</h2>

Accessing the dialog from Javascript is made as follows:

```javascript
var UI = new UbuntuUI();
UI.init();
var dialog = UI.dialog('dialogId'); // Takes an "id"-String as a parameter. 
```html


<h2>Interface definition</h2>

```javascript
interface Dialog{
  void show();
  void hide();
  void toggle();
};
```


<h2>Methods</h2>

<dl>
<dt>void show()</dt>
<dd>shows the dialog.</dd>

<dt>void hide()</dt>
<dd>hides the dialog.</dd>

<dt>void toggle()</dt>
<dd>shows the dialog if it is hidden, hides if it is shown.</dd>

</dl>

Dialogs can be shown and hidden from Javascript as follows:

```javascript
UI.dialog('dialogId').show(); // show the dialog
UI.dialog('dialogId').hide(); // hides the dialog
UI.dialog('dialogId').toggle(); // toggles the state to "displayed" or "hidden"
```


<h2>Predefined CSS classes</h2>

<ul>
<li><code>shake</code>: this class is an animation which "shakes" the dialog. Use it for example when the user entered some data which cannot be validated.</li>
</ul>

The following example shakes the dialog when the user tries to save an empty name:

```html
<div id="dialog" style="display: block" data-role="dialog">
  <section>
    <h1>Name Dialog</h1>
    <p>What is your name?</p>
    <menu>
      <input type="text" id="nameField"/>
      <button data-role="button" id="okButton">OK<button>
    </menu>
  </section>
<div>
<script>
UI.button('okButton').click(function(){
  var name = document.getElementById('nameField').value;
  if(!name){
    // displays a shake animation because the user forgot to enter his name
    document.getElementById('dialog').classList.add("shake");
  }
});
</script>
```