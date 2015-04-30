---
layout: post
title:  "Ubuntu HTML5 platform: buttons, dialogs, sliders"
date:   2013-09-07 21:20:00
categories: Ubuntu HTML5
---
In the <a href="taming-the-ubuntu-html5-platform-part-2/">last article</a>, I explained pagestacks, pages, and the machinery behind the back-button and its "history" functionality.

In this part, we will look at the different predefined widgets that can be used in an Ubuntu HTML5 application.

<h1 id="buttons">Buttons</h1>
Buttons are declared as follows in the HTML5 markup:

[sourcecode language="html"]
<button data-role="button" id="myButton">Standard</button>
[/sourcecode]

Ubuntu HTML5 Theme comes with predefined classes to style buttons. They are named "success", "danger" and "warning".

This code:
```html
<button data-role="button" id="myButton">Standard</button>
<button class="success" data-role="button">Call</button>
<button class="danger" data-role="button">Delete</button>
<button class="warning" data-role="button">Warning</button>
```

They look like this in the web-browser:

[caption id="attachment_678" align="alignnone" width="300"]<a href="http://daniel-beck.org/wp-content/uploads/buttonsStyles.png"><img class="size-medium wp-image-678" alt="The different predefined classes for buttons" src="http://daniel-beck.org/wp-content/uploads/buttonsStyles-300x30.png" width="300" height="30" /></a> The different predefined classes for buttons[/caption]

Listening to a click-event is done as follows:
```javascript
UI.button('myButton').click(function(){
  alert("Button clicked");
});
```

<h1 id="dialogs">Dialogs</h1>
Dialogs are the equivalent of native modal dialogs. They disallow any other interaction with the application. First, the user has to react to them.

Here is an example showing a simple "yes/no" dialog:

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

[caption id="attachment_693" align="alignnone" width="300"]<a href="http://daniel-beck.org/wp-content/uploads/dialog.png"><img class="size-medium wp-image-693" alt="Cancel/Delete dialog" src="http://daniel-beck.org/wp-content/uploads/dialog-300x161.png" width="300" height="161" /></a> Cancel/Delete dialog[/caption]

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
<div>
```

A nice "shake" CSS animation class is included. The following example shakes the dialog from above when the user tries to save an empty name:

```javascript
UI.button('okButton').click(function(){
  var name = document.getElementById('nameField').value;
  if(!name){
    document.getElementById('dialogId').classList.add("shake");
  }
});
```

[caption id="attachment_702" align="alignnone" width="300"]<a href="http://daniel-beck.org/wp-content/uploads/dialogTextInput.png"><img class="size-medium wp-image-702" alt="Prompt Dialog" src="http://daniel-beck.org/wp-content/uploads/dialogTextInput-300x159.png" width="300" height="159" /></a> Prompt Dialog[/caption]

Dialogs can be shown and hidden from Javascript as follows:

```javascript
UI.dialog('dialogId').show(); // show the dialog
UI.dialog('dialogId').hide(); // hides the dialog
UI.dialog('dialogId').toggle(); // toggles the state to "displayed" or "hidden"
```

<h1 id="sliders">Sliders</h1>
Sliders are horizontal and have a single handle that can be moved with the mouse or the touch screen. They are declared in the HTML markup as follows:

```HTML
<input id="myslider" type="range" value="0" max="100" min="0" name="formvalue">
```

Additionally, the result of the selected value can be shown in an output-field like this:
```HTML
<form onsubmit="return false" oninput="displayedAge.value = age.valueAsNumber">
	<input name="age" id="age" type="range" min="0" max="100" value="0">
	<output for="age" name="displayedAge">0</output>
</form>
```

Using a slider with an output element looks like this:

<a href="http://daniel-beck.org/wp-content/uploads/slider.png"><img class="size-full wp-image-710" alt="A slider" src="http://daniel-beck.org/wp-content/uploads/slider.png" width="234" height="49" /></a>
<div class="box">
<h2>New in HTML5: the output tag</h2>
The output-tag mentioned above is a new HTML5 element which can be bound to an input field (like "text" and "range") inside a form element. It performs a calculation on it and shows the result in the output-tag.

More information on it can be found <a href="https://developer.mozilla.org/docs/Web/HTML/Element/output">here</a>.

</div>
Ubuntu HTML5 has no Javascript utilities for sliders.
<h1>Conlusion</h1>
In the <a href="taming-the-ubuntu-html5-platform-part-2/">last article</a>, we looked at the basic building blocks: pagestacks, pages and the back-button. In this article, we examined buttons, dialogs and sliders. The next article will focus on textfields, popover-menus and lists.