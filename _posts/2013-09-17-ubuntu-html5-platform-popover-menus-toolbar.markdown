---
layout: post
title:  "Ubuntu HTML5 platform: popover menus and toolbar"
date:   2013-09-17 19:54:00
categories: Ubuntu HTML5
---
This is the next article from the series about the <a href="http://daniel-beck.org/category/ubuntu-html5/">Ubuntu HTML5 platform</a>. This time, we focus on popover menus and on the toolbar.
<h1>Popover menu</h1>
Popover menus kind of look like speech bubbles. They are "attached" to an element and open next to it. the way they open is controlled by the attribute <code>data-gravity</code>:
<ul>
<li><code>gravity=n</code> (north), i.e. the speech bubbles tail points to the top of the browser viewport</li>
<li><code>gravity=s</code> (south), i.e. the speech bubbles tail points to the bottom of the browser viewport</li>
<li><code>gravity=e</code> (east), i.e. the speech bubbles tail points to the right of the browser viewport</li>
<li><code>gravity=w</code> (west), i.e. the speech bubbles tail points to the left of the browser viewport</li>
</ul>

Here is a picture of the different options:
<a href="http://daniel-beck.org/wp-content/uploads/FourPopoverMenus.png"><img src="http://daniel-beck.org/wp-content/uploads/FourPopoverMenus.png" alt="FourPopoverMenus" width="583" height="142" class="alignnone size-full wp-image-1122" /></a>

The picture above was made with the following HTML markup:

<pre>
&lt;div class="popover active" data-gravity="n" style="top:10px; left:10px; width:130px"&gt;
  &lt;ul class="list"&gt;
    &lt;li class="active"&gt;&lt;a href="#"&gt;Item1&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a href="#"&gt;Item2&lt;/a&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;
&lt;div class="popover active" data-gravity="s" style="top:10px; left:150px; width:130px"&gt;
  &lt;ul class="list"&gt;
    &lt;li class="active"&gt;&lt;a href="#"&gt;Item1&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a href="#"&gt;Item2&lt;/a&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;
&lt;div class="popover active" data-gravity="e" style="top:10px; left:300px;width:130px"&gt;
  &lt;ul class="list"&gt;
    &lt;li class="active"&gt;&lt;a href="#"&gt;Item1&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a href="#"&gt;Item2&lt;/a&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;
&lt;div class="popover active" data-gravity="w" style="top:10px; left:450px; width:130px"&gt;
  &lt;ul class="list"&gt;
    &lt;li class="active"&gt;&lt;a href="#"&gt;Item1&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a href="#"&gt;Item2&lt;/a&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;
</pre>


You can try and edit this code on JS Bin: <a href="http://jsbin.com/akUZIto/2/edit">JS Bin - Four popover menus</a>

This code displays four popover menus; each one is made of two list items. They are made visible by setting <code>class="active"</code>. Popover menus without <code>class="active"</code> are not shown!

Popover menus are positioned absolutely, thus they need the "left" and "top" style attributes. In practice, the app developer almost never need to compute these attributes, since they are computed automatically with <code>List.prototype.show()</code>:

<pre>
var button = UI.button("myButton");
UI.popover(button, "popover1").show();
</pre>

The method <code>show()</code> does two things: 
<ol>
<li>It adds "active" to the classlist of the popover menu. This makes the element visible. </li>
<li>It computes the "top" and "left" style parameters, so that the popover menu opens next to the button and according to its <code>data-gravity</code> attribute.</li>
</ol>

There is also an <code>hide()</code> and a <code>toggle()</code> method, to hide or toggle a popover menu element.

As an example, the following code opens a popover menu above a button and closes it as soon as the user clicks the other button.

<pre>
&lt;button data-role="button" id="button1"&gt;Button 1&lt;/button&gt;
&lt;button data-role="button" id="button2"&gt;Button 2&lt;/button&gt;
&lt;div id="popover1" class="popover" data-gravity="s"&gt;
  &lt;ul class="list"&gt;
    &lt;li class="active"&gt;&lt;a href="#"&gt;Item1&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a href="#"&gt;Item2&lt;/a&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;
&lt;div id="popover2" class="popover" data-gravity="s"&gt;
  &lt;ul class="list"&gt;
    &lt;li class="active"&gt;&lt;a href="#"&gt;Item1&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a href="#"&gt;Item2&lt;/a&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;

&lt;script&gt;
var button1 = UI.button("button1");
button1.click(function() {
  UI.popover(this, "popover1").toggle();
  UI.popover(this, "popover2").hide();
});

var button2 = UI.button("button2");
button2.click(function (){
    UI.popover(this, "popover2").toggle();
    UI.popover(this, "popover1").hide();
});
&lt;/script&gt;
</pre>

You can try and edit this code on JS Bin: <a href="http://jsbin.com/EDENANA/8/edit">JS Bin - Opening and closing popover menus</a>

<h1>Toolbar</h1>
The toolbar lives at the bottom edge of the screen as a footer. It contains icons that engender actions whenever the user clicks on them.

While it is technically possible to put more than five icons on the toolbar, the Ubuntu Touch guidelines specifies that <a href="http://design.ubuntu.com/apps/building-blocks/toolbar">the maximum number of icons is five</a>.

The toolbar is defined as follows:
<pre>
&lt;footer id="footer" class="revealed" data-role="footer"&gt;
  &lt;nav&gt;
    &lt;ul&gt;
      &lt;li&gt;&lt;a href="#"&gt;&lt;span&gt;Add Feed&lt;/span&gt;&lt;/li&gt;
      &lt;li&gt;&lt;span&gt;Delete Feed&lt;/span&gt;&lt;/li&gt;
      &lt;li&gt;&lt;img alt="Tap me!" src="../../ambiance/img/back@18.png"&gt;&lt;span&gt;Back&lt;/span&gt;&lt;/li&gt;
    &lt;/ul&gt;
  &lt;/nav&gt;
&lt;/footer&gt;
</pre>

The classname <code>revealed</code> indicates that the toolbar is shown.
The <a href="http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-2#backbutton">backbutton</a> is created automatically by the Ubuntu HTML5 theme when the application starts (if a toolbar was defined in the HTML markup).

Ubuntu HTML5 comes with several methods to show and hide the toolbar:

<pre>
UI.toolbar("footer").show(); 
UI.toolbar("footer").hide();
UI.toolbar("footer").toggles(); 
 // Registers an event handler for touch-release events (or mouse-up event on desktop)
UI.toolbar("footer").touch(handlerFunc);
</pre>

According to the user interface guidelines, the toolbar should be shown and hidden by touching it. This is realized with the following code:

<pre>
var toolbar = UI.toolbar("footer");
toolbar.touch( function(){
  toolbar.toggle();
});
</pre>

This can also be tried out live: <a href="http://jsbin.com/elaZiFI/2/edit">JS Bin - Toggline the toolbar on touch events</a>

Unfortunately, there are no predefined javascript methods to add new buttons to the toolbar or remove them from it. For example, this might be useful in an  email-application where the buttons "new email" and "refresh" are shown on the main page, and the buttons "send email" and "save as draft" on the "compose" page.

I implemented two methods to add and remove buttons to the toolbar at runtime: 
<ul>
<li><code>addActionToToolbar(id, text, onclick, buttonId, img)</code>: Adds a button labeled with "text" to the toolbar, and associates it with the onclick event handler. The actionid and the image are optional.</li>
<li><code>removeActionFromToolbar(buttonId)</code>: Removes a  button from the toolbar.</li>
</ul>

The implemented methods can be found here:
<a href="http://jsbin.com/exIVIDu/6/edit">JS Bin - Methods to add actions to the toolbar</a>.