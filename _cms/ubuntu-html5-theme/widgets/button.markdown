---
layout: post
title:  Button
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---

<h2>Overview</h2>
<code>Button</code> objects represent Ubuntu HTML5 buttons. They offer a click event handler and CSS classes to style them.

<h2>Markup declaration</h2>

```html
<button data-role="button" id="myButton">Standard</button>
```


<h2>Javascript access method</h2>
Accessing the button is made as follows:

```javascript
var UI = new UbuntuUI();
UI.init();
var button = UI.button("id");
```

<h2>Interface definition</h2>

```javascript
interface Button{
  void click(AsyncOperationCallback callback);
};
```

<h2>Method</h2>

<dl>
<dt>void click(AsyncOperationCallback callback)</dt>
<dd>registers a listener for <code>click</code> events. The implementation uses the <a href="http://daniel-beck.org/ubuntu-html5-theme/other-apis/fastbutton/">FastButton</a> class. On devices with touch displays, the <code>click</code> event is emulated and triggered whenever a <code>touchend</code> event occurs within a small timeframe after a <code>touchstart</code> event. This behavior is implemented by the <code>FastButton</code> class and described there. See class: <a href="http://daniel-beck.org/ubuntu-html5-theme/other-apis/fastbutton/">FastButton</a>.</dd>
</dl>


The following example registers an event handler for (emulated) click events:

```javascript
UI.button('myButton').click(function(){
  alert("Button clicked");
});
```

<h2>Predefined CSS classes</h2>

Ubuntu HTML5 Theme comes with predefined classes to style buttons. They are named:

<ul>
<li>success</li>
<li>danger</li> 
<li>warning</li>
</ul>

Here are the CSS classes in action:

```html
<button data-role="button" >Standard</button>
<button class="success" data-role="button">Call</button>
<button class="danger" data-role="button">Delete</button>
<button class="warning" data-role="button">Warning</button>
```

Here is the result of styling the buttons:
[caption id="attachment_678" align="alignnone" width="423"]<a href="http://daniel-beck.org/wp-content/uploads/buttonsStyles.png"><img src="http://daniel-beck.org/wp-content/uploads/buttonsStyles.png" alt="The different predefined classes for buttons" width="423" height="43" class="size-full wp-image-678" /></a> Predefined classes for buttons[/caption]