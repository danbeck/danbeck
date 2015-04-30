---
layout: post
title:  "Ubuntu HTML5 platform: Header, Progress bars, Text inputs, Ubuntu Shapes"
date:   2013-09-24 18:39:00
categories: Ubuntu HTML5
---
This is one further article about the <a href="http://daniel-beck.org/category/ubuntu-html5/">Ubuntu HTML5 platform</a> and the last article on widgets. We will examine the application header, progress bars, text inputs and ubuntu shapes.

<h2>Header</h2>
The <a href="http://design.ubuntu.com/apps/building-blocks/header">header</a> is an UI component which sits on top of an application.  It
<ul>
<li>shows the user, where he is </li>
<li>switches tabs, which are views of equal importance (see the <a href="http://design.ubuntu.com/apps/building-blocks/tabs">guidelines</a>)</li>
</ul>

To show a header containing several tabs, 
<ul>
<li>create a <code>section</code> container having an attribute <code>data-role="header"</code></li>
<li>add list items to that section-element having the attribute <code>data-role="tab"</code></li>
</ul>

Here is explanatory code snippet:

<pre>
&lt;header data-role="header"&gt;
  &lt;nav class="tabs" data-role="navbar"&gt;
    &lt;div class="tabs-inner"&gt;
      &lt;ul data-role="tabs"&gt;
        &lt;li class="active" data-role="tab"&gt;
          &lt;a href="#item1" id="firstTab"&lt;First&lt;/a&gt;
        &lt;/li&gt;
        &lt;li class="inactive" data-role="tab"&gt;
          &lt;a href="#item2" id="secondTab"&gt;Second&lt;/a&gt;
        &lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;
  &lt;/nav&gt;
&lt;/header&gt;

</pre>

And here is a screenshot of such a header UI element:

[caption id="attachment_1215" align="alignnone" width="333"]<a href="http://daniel-beck.org/wp-content/uploads/Header.png"><img src="http://daniel-beck.org/wp-content/uploads/Header.png" alt="Header" width="333" height="71" class="size-full wp-image-1215" /></a> Header[/caption]

There is no predefined UI method to bind a callback function to a tab, yet. So, I created a small example to show how to switch pages when the user clicks on a tab:  <a href="http://jsbin.com/IBeniXo/2/edit">JS Bin - Header and tabs</a>. 

<h2>Progress bars</h2>
Progress bars are new HTML5 elements. Ubuntu HTML5 comes with CSS styling instructions to style them.

Declaring progress bars is made as follows:

<pre>
&lt;progress&gt;&lt;/progress&gt;
&lt;progress class="bigger"&gt;&lt;/progress&gt;
</pre>

Here is a link to try out progress bars on JS Bin: <a href="http://jsbin.com/UlAtiSO/3/edit">JS Bin - Progress bars</a>

Progress bars with attributes like <code>"value"</code> or <code>"max"</code> are not styled yet (as of Ubuntu HTML5 Theme version 0.1). Here is an example that will NOT be styled correctly:
<pre>
&lt;progress max="100" value="80"&gt;&lt;/progress&gt;
</pre>

<h2>Text inputs</h2>
HTML5 brings new input types like "number", "url", "email", etc. These new input types have several advantages: 
<ul>
<li>Different on screen-keyboards might be used. For example, "numbers" might be entered with a numeric keyboard.</li>
<li>The input can be validated by the browser before submitting a form to a server. E.g. the type "email" will show an error when the user tries to submit an email address without a "@"-character.</li>
</ul>
 
Here are some examples to show the individual input types: 
<pre>
&lt;div class="inset"&gt;
  &lt;input type="text" placeholder="simple text field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="text" disabled="" placeholder="disabled text field"&gt;
&lt;/div&lt;
&lt;div class="inset"&gt;
  &lt;input type="tel" placeholder="telephone field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="search" placeholder="search field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="number" placeholder="number field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="url" placeholder="url field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="password" placeholder="password with echo"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;textarea placeholder="the placeholder text is a text which is displayed when there is no content in the TextArea"&gt;&lt;/textarea&gt;
&lt;/div&gt;
</pre>

This code can be tried online: <a href="http://jsbin.com/evAMIvi/1/edit">JS Bin - Inputs types</a>.

No UI methods are needed to access the values of these input fields, <code>document.getElementById("elementid").value</code> suffices.


<h2>Shapes</h2>
Shapes are "decorators" to make elements like images look as follows:
[caption id="attachment_1216" align="alignnone" width="106"]<a href="http://daniel-beck.org/wp-content/uploads/UbuntuShape.png"><img src="http://daniel-beck.org/wp-content/uploads/UbuntuShape.png" alt="Ubuntu Shape" width="106" height="109" class="size-full wp-image-1216" /></a> Ubuntu Shape[/caption]

Using them is simple:

<pre>
&lt;div data-role="shape"&gt;
  &lt;img src="http://cordova.apache.org/images/cordova_bot.png"&gt;
&lt;/div&gt;
</pre>

Since Shapes are created by using images, setting height and width might make them look bad. 

The example can be tried online here: <a href="http://jsbin.com/oPUpuMo/1/edit">JS Bin - Shapes</a>


The next article will focus on the storage options "localstorage", "WebSQL", and "IndexedDB".

&lt;header data-role="header"&gt;
  &lt;nav class="tabs" data-role="navbar"&gt;
    &lt;div class="tabs-inner"&gt;
      &lt;ul data-role="tabs"&gt;
        &lt;li class="active" data-role="tab"&gt;
          &lt;a href="#item1" id="firstTab"&lt;First&lt;/a&gt;
        &lt;/li&gt;
        &lt;li class="inactive" data-role="tab"&gt;
          &lt;a href="#item2" id="secondTab"&gt;Second&lt;/a&gt;
        &lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;
  &lt;/nav&gt;
&lt;/header&gt;

</pre>

And here is a screenshot of such a header UI element:

[caption id="attachment_1215" align="alignnone" width="333"]<a href="http://daniel-beck.org/wp-content/uploads/Header.png"><img src="http://daniel-beck.org/wp-content/uploads/Header.png" alt="Header" width="333" height="71" class="size-full wp-image-1215" /></a> Header[/caption]

There is no predefined UI method to bind a callback function to a tab, yet. So, I created a small example to show how to switch pages when the user clicks on a tab:  <a href="http://jsbin.com/IBeniXo/2/edit">JS Bin - Header and tabs</a>. 

<h2>Progress bars</h2>
Progress bars are new HTML5 elements. Ubuntu HTML5 comes with CSS styling instructions to style them.

Declaring progress bars is made as follows:

<pre>
&lt;progress&gt;&lt;/progress&gt;
&lt;progress class="bigger"&gt;&lt;/progress&gt;
</pre>

Here is a link to try out progress bars on JS Bin: <a href="http://jsbin.com/UlAtiSO/3/edit">JS Bin - Progress bars</a>

Progress bars with attributes like <code>"value"</code> or <code>"max"</code> are not styled yet (as of Ubuntu HTML5 Theme version 0.1). Here is an example that will NOT be styled correctly:
<pre>
&lt;progress max="100" value="80"&gt;&lt;/progress&gt;
</pre>

<h2>Text inputs</h2>
HTML5 brings new input types like "number", "url", "email", etc. These new input types have several advantages: 
<ul>
<li>Different on screen-keyboards might be used. For example, "numbers" might be entered with a numeric keyboard.</li>
<li>The input can be validated by the browser before submitting a form to a server. E.g. the type "email" will show an error when the user tries to submit an email address without a "@"-character.</li>
</ul>
 
Here are some examples to show the individual input types: 
<pre>
&lt;div class="inset"&gt;
  &lt;input type="text" placeholder="simple text field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="text" disabled="" placeholder="disabled text field"&gt;
&lt;/div&lt;
&lt;div class="inset"&gt;
  &lt;input type="tel" placeholder="telephone field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="search" placeholder="search field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="number" placeholder="number field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="url" placeholder="url field"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;input type="password" placeholder="password with echo"&gt;
&lt;/div&gt;
&lt;div class="inset"&gt;
  &lt;textarea placeholder="the placeholder text is a text which is displayed when there is no content in the TextArea"&gt;&lt;/textarea&gt;
&lt;/div&gt;
</pre>

This code can be tried online: <a href="http://jsbin.com/evAMIvi/1/edit">JS Bin - Inputs types</a>.

No UI methods are needed to access the values of these input fields, <code>document.getElementById("elementid").value</code> suffices.


<h2>Shapes</h2>
Shapes are "decorators" to make elements like images look as follows:
[caption id="attachment_1216" align="alignnone" width="106"]<a href="http://daniel-beck.org/wp-content/uploads/UbuntuShape.png"><img src="http://daniel-beck.org/wp-content/uploads/UbuntuShape.png" alt="Ubuntu Shape" width="106" height="109" class="size-full wp-image-1216" /></a> Ubuntu Shape[/caption]

Using them is simple:

<pre>
&lt;div data-role="shape"&gt;
  &lt;img src="http://cordova.apache.org/images/cordova_bot.png"&gt;
&lt;/div&gt;
</pre>

Since Shapes are created by using images, setting height and width might make them look bad. 

The example can be tried online here: <a href="http://jsbin.com/oPUpuMo/1/edit">JS Bin - Shapes</a>


The next article will focus on the storage options "localstorage", "WebSQL", and "IndexedDB".
