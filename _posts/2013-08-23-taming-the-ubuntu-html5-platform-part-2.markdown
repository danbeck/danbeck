---
layout: post
title:  "Ubuntu HTML5 platform: pagestack, pages and the back-button"
date:   2013-08-28 09:49:00
categories: Ubuntu HTML5
---
Intoduction
------------

In the <a href="taming-the-ubuntu-html5-platform-part1/">first part</a>, I gave an overview over Apache Cordova and the Ubuntu HTML5 Theme.

In this part, I introduce some fundamental concepts of the Ubuntu HTML5 Theme. I also show its most fundamental widgets: _pagestacks_, _page_ and the _back-button_.

Styling HTML5 elements
---------------------

Ubuntu HTML5 Widgets are regular HTML5 elements which are styled by assigning them predefined CSS classes with _data-role_ attributes.
The "data-role" attribute is a <a href="http://www.w3.org/TR/2011/WD-html5-20110525/elements.html#embedding-custom-non-visible-data-with-the-data-attributes">custom data attribute</a>, a W3C Working draft. Custom data attributes hold metadata and begin with "data-*". They can simplify javascript code. For example, <code>&lt;button data-number-of-clicks="3"/&gt;</code> stores the number of times clicked on that button. Before HTML5, this was often realized with the attributes "rel" or "classnames".</p>

As a rule of thumb, if a Ubuntu HTML5 widget has no associated behavior, it only uses CSS classes. For example, the widget "toggle" styles an inline-element like "&lt;span&gt;" to look like a toggle. If it has some javascript behavior, it uses a "data-role" attribute.

An example for a widget with such a predefined behavior is the back button. Its associated behavior is to switch back to the last displayed page.
<h1 id="pagestack">Pagestack and pages</h1>
Pagestack and pages are a central concept of the Ubuntu HTML5 Theme. Understanding them is crucial for writing an Ubuntu HTML5 applications.

In HTML5 applications, there is only one HTML page. No other page can be displayed. Instead, HTML5 applications emulate this by having several div-containers acting like pages. Only one of them is displayed at the same time, the other ones are hidden. This is realized by setting the containers "display"-attribute to "block" to display them, and to "none" to hide them. "display:none" is a style declaration that makes an element invisible and removes it from the page flow.

The Ubuntu HTML5 Theme uses "pagestack" as a container for "pages". It has a set of prototypes and javascript functions to handle them. <code>UI.pagestack("thispage")</code> selects the page with the id <code>"thispage"</code>. With <code>UbuntuUI.pagestack("thispage").push()</code> that page is shown and all other pages are hidden.

Here is a code snippet with a pagestack contains two pages. Each of them contains a button. Clicking the button shows one page, and hides the other one.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link href="/usr/share/ubuntu-html5-theme/0.1/ambiance/css/appTemplate.css"
          rel="stylesheet"/>
    <script src="/usr/share/ubuntu-html5-theme/0.1/ambiance/js/core.js"></script>
    <script src="/usr/share/ubuntu-html5-theme/0.1/ambiance/js/pagestacks.js"></script>
    <script src="/usr/share/cordova-ubuntu-2.8/www/cordova-2.8.js"></script>
  </head>

  <body>
    <div data-role="pagestack">
      <div data-role="page" id="firstpage">
      <button id="button1">switch to page #2</button>
    </div>
    <div data-role="page" id="secondpage">
      <button id="button2">switch to page #1</button>
    </div>
  </div>
  <script>
// initializes the Ubuntu HTML5 Theme
var UI = new UbuntuUI();
UI.init();

var button1 = document.getElementById("button1");
button1.addEventListener("click", function() {
  UI.pagestack.push("secondpage");
});

var button2 = document.getElementById("button2");
button2.addEventListener("click", function() {
  UI.pagestack.push("firstpage");
});
</script>
</body>
</html>
```

<h1 id="backbutton">The backbutton</h1>
Another, really useful feature of the Ubuntu HTML5 theme is the "back-button". This button gets automatically added to the toolbar at the bottom of the screen:

![The back button]({{ site.baseurl }}/images/Backbutton-300x37.png)

To realize the functionality to go backward to a previous page, the Ubuntu HTML5 Theme maintains a stack of "pages", named the <code>Pagestack</code>.

When a UbuntuUI object is initialized, the pagestack is empty. If there is a footer, a back-button is automatically added to it. This is the reason why it is necessary to call <code>UbuntuUI.init()</code> at the start of an application.
From now on, each time the application calls <code>UbuntuUI.pagestack("pageid").push()</code> to show a page, the <code>id</code> of that page is put on the pagestack.

The back-button (which is declared with the attribute <code>"data-role=back"</code>) pops the last id from the page-stack. Then, the preceding page is shown. However, there is no forward functionality.

The fundamentals having now being explained, the next part will focus on the other following widgets: buttons, dialogs, sliders, popover menus, lists, checkboxes and switches, headers and textfields.