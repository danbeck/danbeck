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
Checkboxes are _&lt;input&gt;_ HTML elements having the attribute _type="checkbox"_. They must be followed by an empty span element (This is needed by the CSS to set the checkbox image):

```html
<label>
  <input type="checkbox" checked="checked" />
  <span></span>
</label>
```

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

![Ubuntu HTML5 checkboxes]({{ site.baseurl }}/images/Checkboxes.png)


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

![Ubuntu HTML5 switches]({{ site.baseurl }}/images/Switches.png)

<h2>Javascript access method</h2>
Currently, toggles have no access methods in <a href="{{ site.baseurl }}/ubuntu-html5-theme/widgets/ubuntu-ui/">UbuntuUI</a>.

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

* _void isChecked()_. returns true if the toggle is checked, false otherwise.

* _void check()_ checks the toggle.

* _void uncheck()_. unchecks the toggle.

* _void toggle()_. checks the toggle if it is unchecked, unchecks it if it is checked.