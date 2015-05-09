---
layout: post
title:  "Ubuntu HTML5 platform: Header, Progress bars, Text inputs, Ubuntu Shapes"
date:   2013-09-24 18:39:00
categories: Ubuntu HTML5
---
This is one further article about the <a href="http://daniel-beck.org/category/ubuntu-html5/">Ubuntu HTML5 platform</a> and the last article on widgets. We will examine the application header, progress bars, text inputs and ubuntu shapes.

Header
----------

The <a href="http://design.ubuntu.com/apps/building-blocks/header">header</a> is an UI component which sits on top of an application.  It

 * shows the user, where he is 
 * switches tabs, which are views of equal importance (see the <a href="http://design.ubuntu.com/apps/building-blocks/tabs">guidelines</a>)

To show a header containing several tabs, 

 * create a <code>section</code> container having an attribute <code>data-role="header"</code>
 * add list items to that section-element having the attribute <code>data-role="tab"</code>

Here is explanatory code snippet:

```html
<header data-role="header">
  <nav class="tabs" data-role="navbar">
    <div class="tabs-inner">
      <ul data-role="tabs">
        <li class="active" data-role="tab">
          <a href="#item1" id="firstTab"<First</a>
        </li>
        <li class="inactive" data-role="tab">
          <a href="#item2" id="secondTab">Second</a>
        </li>
      </ul>
    </div>
  </nav>
</header>
```

And here is a screenshot of such a header UI element:

[caption id="attachment_1215" align="alignnone" width="333"]<a href="http://daniel-beck.org/wp-content/uploads/Header.png"><img src="http://daniel-beck.org/wp-content/uploads/Header.png" alt="Header" width="333" height="71" class="size-full wp-image-1215" /></a> Header[/caption]

There is no predefined UI method to bind a callback function to a tab, yet. So, I created a small example to show how to switch pages when the user clicks on a tab:  <a href="http://jsbin.com/IBeniXo/2/edit">JS Bin - Header and tabs</a>. 

Progress bars
---------------

Progress bars are new HTML5 elements. Ubuntu HTML5 comes with CSS styling instructions to style them.

Declaring progress bars is made as follows:

```html
<progress></progress>
<progress class="bigger"></progress>
```

Here is a link to try out progress bars on JS Bin: <a href="http://jsbin.com/UlAtiSO/3/edit">JS Bin - Progress bars</a>

Progress bars with attributes like <code>"value"</code> or <code>"max"</code> are not styled yet (as of Ubuntu HTML5 Theme version 0.1). Here is an example that will NOT be styled correctly:

```html
<progress max="100" value="80"></progress>
```

Text inputs
--------------
HTML5 brings new input types like "number", "url", "email", etc. These new input types have several advantages: 


* Different on screen-keyboards might be used. For example, "numbers" might be entered with a numeric keyboard.
* The input can be validated by the browser before submitting a form to a server. E.g. the type "email" will show an error when the user tries to submit an email address without a "@"-character.
 
Here are some examples to show the individual input types: 

```html
<div class="inset">
  <input type="text" placeholder="simple text field">
</div>
<div class="inset">
  <input type="text" disabled="" placeholder="disabled text field">
</div<
<div class="inset">
  <input type="tel" placeholder="telephone field">
</div>
<div class="inset">
  <input type="search" placeholder="search field">
</div>
<div class="inset">
  <input type="number" placeholder="number field">
</div>
<div class="inset">
  <input type="url" placeholder="url field">
</div>
<div class="inset">
  <input type="password" placeholder="password with echo">
</div>
<div class="inset">
  <textarea placeholder="the placeholder text is a text which is displayed when there is no content in the TextArea"></textarea>
</div>
```

This code can be tried online: <a href="http://jsbin.com/evAMIvi/1/edit">JS Bin - Inputs types</a>.

No UI methods are needed to access the values of these input fields, <code>document.getElementById("elementid").value</code> suffices.


Shapes
------------

Shapes are "decorators" to make elements like images look as follows:
[caption id="attachment_1216" align="alignnone" width="106"]<a href="http://daniel-beck.org/wp-content/uploads/UbuntuShape.png"><img src="http://daniel-beck.org/wp-content/uploads/UbuntuShape.png" alt="Ubuntu Shape" width="106" height="109" class="size-full wp-image-1216" /></a> Ubuntu Shape[/caption]

Using them is simple:

```html
<div data-role="shape">
  <img src="http://cordova.apache.org/images/cordova_bot.png">
</div>
```

Since Shapes are created by using images, setting height and width might make them look bad. 

The example can be tried online here: <a href="http://jsbin.com/oPUpuMo/1/edit">JS Bin - Shapes</a>


The next article will focus on the storage options "localstorage", "WebSQL", and "IndexedDB".

```html
<header data-role="header">
  <nav class="tabs" data-role="navbar">
    <div class="tabs-inner">
      <ul data-role="tabs">
        <li class="active" data-role="tab">
          <a href="#item1" id="firstTab"<First</a>
        </li>
        <li class="inactive" data-role="tab">
          <a href="#item2" id="secondTab">Second</a>
        </li>
      </ul>
    </div>
  </nav>
</header>

```

And here is a screenshot of such a header UI element:

[caption id="attachment_1215" align="alignnone" width="333"]<a href="http://daniel-beck.org/wp-content/uploads/Header.png"><img src="http://daniel-beck.org/wp-content/uploads/Header.png" alt="Header" width="333" height="71" class="size-full wp-image-1215" /></a> Header[/caption]

There is no predefined UI method to bind a callback function to a tab, yet. So, I created a small example to show how to switch pages when the user clicks on a tab:  <a href="http://jsbin.com/IBeniXo/2/edit">JS Bin - Header and tabs</a>. 

Progress bars
------------

Progress bars are new HTML5 elements. Ubuntu HTML5 comes with CSS styling instructions to style them.

Declaring progress bars is made as follows:

```html
<progress></progress>
<progress class="bigger"></progress>
```
Here is a link to try out progress bars on JS Bin: <a href="http://jsbin.com/UlAtiSO/3/edit">JS Bin - Progress bars</a>

Progress bars with attributes like <code>"value"</code> or <code>"max"</code> are not styled yet (as of Ubuntu HTML5 Theme version 0.1). Here is an example that will NOT be styled correctly:
 
```html
<progress max="100" value="80"></progress>
```

<h2>Text inputs</h2>
HTML5 brings new input types like "number", "url", "email", etc. These new input types have several advantages: 

 * Different on screen-keyboards might be used. For example, "numbers" might be entered with a numeric keyboard.
 * The input can be validated by the browser before submitting a form to a server. E.g. the type "email" will show an error when the user tries to submit an email address without a "@"-character.
 
Here are some examples to show the individual input types: 
```html
<div class="inset">
  <input type="text" placeholder="simple text field">
</div>
<div class="inset">
  <input type="text" disabled="" placeholder="disabled text field">
</div<
<div class="inset">
  <input type="tel" placeholder="telephone field">
</div>
<div class="inset">
  <input type="search" placeholder="search field">
</div>
<div class="inset">
  <input type="number" placeholder="number field">
</div>
<div class="inset">
  <input type="url" placeholder="url field">
</div>
<div class="inset">
  <input type="password" placeholder="password with echo">
</div>
<div class="inset">
  <textarea placeholder="the placeholder text is a text which is displayed when there is no content in the TextArea"></textarea>
</div>
```

This code can be tried online: <a href="http://jsbin.com/evAMIvi/1/edit">JS Bin - Inputs types</a>.

No UI methods are needed to access the values of these input fields, <code>document.getElementById("elementid").value</code> suffices.


<h2>Shapes</h2>
Shapes are "decorators" to make elements like images look as follows:
[caption id="attachment_1216" align="alignnone" width="106"]<a href="http://daniel-beck.org/wp-content/uploads/UbuntuShape.png"><img src="http://daniel-beck.org/wp-content/uploads/UbuntuShape.png" alt="Ubuntu Shape" width="106" height="109" class="size-full wp-image-1216" /></a> Ubuntu Shape[/caption]

Using them is simple:

```html
<div data-role="shape">
  <img src="http://cordova.apache.org/images/cordova_bot.png">
</div>
```

Since Shapes are created by using images, setting height and width might make them look bad. 

The example can be tried online here: <a href="http://jsbin.com/oPUpuMo/1/edit">JS Bin - Shapes</a>


The next article will focus on the storage options "localstorage", "WebSQL", and "IndexedDB".
