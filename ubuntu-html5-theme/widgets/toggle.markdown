---
layout: post
title:  Toggle
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---
<h2>Overview</h2>
<a href="http://design.ubuntu.com/apps/building-blocks/toggles">Toggles</a> are user interface elements which can be turned on and off. They can either be "checkboxes" or "switches".


Toggle is defined in the file <a href="file:///usr/share/ubuntu-html5-theme/0.1/ambiance/js/core.js">/usr/share/ubuntu-html5-theme/0.1/ambiance/js/toggle.js</a>

<h2>Markup declaration</h2>
Checkboxes are <code><input></code> HTML elements having the attribute <code>type="checkbox"</code>. They must be followed by an empty span element (This is needed by the CSS to set the checkbox image):
<pre>
<label>
  <input type="checkbox" checked="checked" />
  <span></span>
</label>
</pre>

Additionaly, checkboxes can have the following attributes:
```html
<ul>
	<li><code>checked</code>: displays the checkbox as "checked"</li>
	<li><code>disabled</code>: disables the checkbox so that its state cannot be changed</li>
</ul>
```

The following code snippets declare checkboxes with the different states:
```html
<div><label>
  <input type="checkbox" checked="checked" />
  <span></span>
</label>
<label>
  <input type="checkbox" />
  <span></span>
</label>
<label>
  <input type="checkbox" checked="checked" disabled="disabled" />
  <span></span>
</label>
<label>
  <input type="checkbox" disabled="disabled" />
  <span></span>
</label></div>
```

This HTML markup looks like this in the browser (from left to right: checked, unchecked, disabled and checked, disabled and unchecked):

[caption id="attachment_805" width="270"]<a href="http://daniel-beck.org/wp-content/uploads/Checkboxes.png"><img class="size-full wp-image-805" alt="Checkboxes" src="http://daniel-beck.org/wp-content/uploads/Checkboxes.png" width="270" height="35" /></a> Checkboxes[/caption]

Switches behave like checkboxes, they only look different. The following HTML markup declares a switch:

```html
<label>
  <input type="checkbox" checked="" data-type="switch">
  <span class="toggle">
    <span class="toggle-handle"></span>
    <span class="toggle-bg"></span>
  </span>
</label>
```

Like checkboxes, switches have the attributes "checked" and "disabled":
[caption id="attachment_839" align="alignnone" width="300"]<a href="http://daniel-beck.org/wp-content/uploads/Switches.png"><img src="http://daniel-beck.org/wp-content/uploads/Switches-300x46.png" alt="Switches" width="300" height="46" class="size-medium wp-image-839" /></a> Switches[/caption]

<h2>Javascript access method</h2>
Currently, toggles have no access methods in <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/ubuntu-ui/">UbuntuUI</a>.

Instead, toggle objects must be created with the <code>Toggle-constructor</code>:

```javascript
var toggle = new Toggle("domId"); //the argument is a global id from the dom
```

<h2>Interface definition</h2>

```javascript
interface Toggle{
  boolean isChecked();
  void check();
  void uncheck();
  void toggle();
};
```



<h2>Methods</h2>

<dl>
<dt>void isChecked()</dt>
<dd>returns true if the toggle is checked, false otherwise.</dd>

<dt>void check()</dt>
<dd>checks the toggle.</dd>

<dt>void uncheck()</dt>
<dd>unchecks the toggle.</dd>

<dt>void toggle()</dt>
<dd>checks the toggle if it is unchecked, unchecks it if it is checked.</dd>
</dl>