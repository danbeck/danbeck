---
layout: post
title:  Popover
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---

<h2>Overview</h2>
Popovers are the equivalent of native popover menus. They can be open over, under, on the left or on the right of an element. They look like this:
<a href="http://daniel-beck.org/wp-content/uploads/FourPopoverMenus.png"><img src="http://daniel-beck.org/wp-content/uploads/FourPopoverMenus.png" alt="FourPopoverMenus" width="583" height="142" class="alignnone size-full wp-image-1122" /></a>

<h2>Markup declaration</h2>
Popovers are <code>div</code> containers which are styled with the class <code>popover</code>. They must have a <code>data-gravity</code> attribute to determine where the popover menu should be opened. Here is an example of a popover menu:

```html
<div class="popover active" data-gravity="n">
  <ul class="list">
    <li class="active"><a href="#">Item1</a></li>
    <li><a href="#">Item2</a></li>
  </ul>
</div>
```

<h2>Javascript Access method</h2>

Accessing the popover from Javascript is made as follows:

```javascript
var UI = new UbuntuUI();
UI.init();
var dialog = UI.popover(document.getElementById('buttonId'), 'dialogId');
```


<h2>Interface definition</h2>

```javascript
interface Popover{
  void show();
  void hide();
  void toggle();
};
```


<h2>Methods</h2>

<dl>
<dt>void show()</dt>
<dd>shows the popover.</dd>

<dt>void hide()</dt>
<dd>hides the popover.</dd>

<dt>void toggle()</dt>
<dd>shows the popover if it is hidden, hides it if it is shown.</dd>

</dl>

<h2>Predefined CSS classes</h2>

<ul>
<li><code>active</code>: this class marks an item in the popover menu as active. By default, the background of that list item is light grey, the color of the text is orange.</li>
</ul>
