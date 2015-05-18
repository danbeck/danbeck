---
layout: post
title:  Toolbar
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---
<h2>Overview</h2>
The toolbar is an UI component which sits at the bottom of an application. It usually contains <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/button/">buttons</a> that engender an action when clicked.
The toolbar is generally contained in a <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/page/">page</a> component or in the <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/pagestack/">pagestack</a>.


While it is technically possible to place more than five icons in the toolbar, the Ubuntu Touch guidelines specify that <a href="http://design.ubuntu.com/apps/building-blocks/toolbar">the maximum number of icons is five</a>.

Here is a screenshot of such a toolbar:
[caption id="attachment_1688" align="alignnone" width="635"]<a href="http://daniel-beck.org/wp-content/uploads/Toolbar.png"><img src="http://daniel-beck.org/wp-content/uploads/Toolbar.png" alt="Toolbar" width="635" height="285" class="size-full wp-image-1688" /></a> Toolbar[/caption]

Toolbar is defined in the file <a href="file:///usr/share/ubuntu-html5-theme/0.1/ambiance/js/toolbar.js">/usr/share/ubuntu-html5-theme/0.1/ambiance/js/toolbar.js</a>

<h2>Markup declaration</h2>

A toolbar is defined as follows:


```html
<footer id="footer" class="revealed" data-role="footer">
  <nav>
    <ul>
      <li><span>Add Feed</span></li>
      <li><span>Delete Feed</span></li>
      <li><img alt="Tap me!" src="../../ambiance/img/back@18.png"><span>Back</span></li>
    </ul>
  </nav>
</footer>
```


<h2>Javascript access method</h2>
Accessing the button is made as follows:

```javascript
var UI = new UbuntuUI();
UI.init();
var toolbar = UI.toolbar("id");
```

<h2>Interface definition</h2>

```javascript
interface Toolbar{
  void show();
  void hide();
  void toggle();
  void touch(AsyncOperationCallback callback);
};
```

<h2>Javascript access method.</h2>

<dl>
<dt>void show()</dt>
<dd>displays the toolbar.</dd>


<dt>void hide()</dt>
<dd>hides the toolbar.</dd>


<dt>void toggle()</dt>
<dd>shows the toolbar if it is hidden, hides it if it is shown.</dd>


<dt>void touch(AsyncOperationCallback callback)</dt>
<dd>Registers a listener for <code>touch</code> events. Usually, the listener calls "toolbar.toggle()" to display or hide the toolbar when the user touches it.</dd>
</dl>

The following example registers an event handler for touch events:

```javascript
UI.toolbar('myToolbar').touch(function(){
  UI.toolbar('myToolbar').toggle();
});
```