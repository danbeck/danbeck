---
layout: post
title:  "Ubuntu UI"
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---
<h2>Overview</h2>
UbuntuUI is the central access point for all Ubuntu Widget classes. It allows to create objects to manipulate all kinds of widgets like "Pagestack", "Buttons" and "Dialogs". Additionally, the role of the <code>UbuntuUI</code> object is to initialize the Ubuntu HTML5 theme. 

Instantiating an UbuntuUI object and initializing the Ubuntu HTML5 theme is usually made when the application starts. The code for it is as follows:


```html
<span class="keyword">var</span> UI = <span class="keyword">new</span> UbuntuUI(); <br>
UI.init();
```

UbuntuUI is defined in the file <a href="file:///usr/share/ubuntu-html5-theme/0.1/ambiance/js/core.js">/usr/share/ubuntu-html5-theme/0.1/ambiance/js/core.js</a>

<h2>Interface definition</h2>

```javascript
interface UbuntuUI {
  Pagestack pagestack;
  void init();
  Button button(DOMString domId);
  Dialog dialog(DOMString domId);
  Popover popover(Element elem, DOMString domId);
  Tabs tabs(DOMString selector);
  Toolbar toolbar(DOMString domId);
  List list(DOMString selector);
};
```

<h2>Attributes</h2>
<dl>
<dt>pagestack: type Pagestack</dt>
<dd><code>pagestack</code> provides access to the <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/pagestack/">Pagestack</a> object, which allows to show and hide <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/page/">Pages</a>. See classes: <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/pagestack/">Pagestack</a> and <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/page/">Page</a>.</dd>
</dl>

<h2>Methods</h2>

<dl>
<dt>void init()</dt>
<dd>should be called at the beginning of each Ubuntu HTML5 application.
 This method creates the application's pagestack with the first element matching the selector <code>[data-role='pagestack']</code>. If the pagestack contains a toolbar - which is the case when the pagestack element has a <code>'footer'</code> node - a back button is added to it. Similarly, for each page contained in the pagestack, if the page has a toolbar, a back button is added to it. If no such toolbar exists, one is created with a back button and appended to the page's DOM.</dd>

<dt>Button button(DOMString domId)</dt>
<dd>creates a new <code>Button</code> object having the global id <code>domId</code>. The created object can be used to add a click-listener to a button. See class: <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/button/">Button</a></dd>

<dt>Dialog dialog(DOMString domId)</dt>
<dd>creates a new <code>Dialog</code> object having the global id <code>domId</code>. The created object can be used to manipulate, show and hide the dialog widget. See class: <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/dialog/">Dialog</a></dd>

<dt>Popover popover(Element elem, DOMString domId)</dt>
<dd>creates a new <code>Popover</code> object having the global id <code>domId</code>. The created object can be used to manipulate a popover menu (e.g. open and close it). The position of the popover menu is calculated by taking in account the position of the element <code>elem</code>. See class: <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/popover/">Popover</a> </dd>

<dt>Tabs tabs(DOMString selector)</dt>
<dd>creates a new <code>Tabs</code> object for the first element within the document that matches the specified <code>selector</code>. See class: <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/tabs/">Tabs</a> </dd>

<dt>Toolbar toolbar(DOMString domId)</dt>
<dd>creates a new <code>Toolbar</code> object having the global id <code>domId</code>. The created object can be used to manipulate the toolbar (e.g. show and hide it). See class: <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/toolbar/">Toolbar</a> </dd>

<dt>List list(DOMString selector)</dt>
<dd>creates a new <code>List</code> object for the first element within the document that matches the specified <code>selector</code>. That element must be a <code>section</code> HTML element, having the attribute <code>data-role="list"</code>. If <code>selector</code> matches a HTML element which is not a <code>section</code> or does not have the attribute <code>data-role="list"</code>, an error is thrown. See class: <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/lists/">List</a> </dd>
</dl>
