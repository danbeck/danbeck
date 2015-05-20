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

<h2>Methods</h2>

* _void click(AsyncOperationCallback callback)_. registers a listener for <code>click</code> events. The implementation uses the <a href="{{ site.baseurl }}/ubuntu-html5-theme/other-apis/fastbutton/">FastButton</a> class. On devices with touch displays, the <code>click</code> event is emulated and triggered whenever a <code>touchend</code> event occurs within a small timeframe after a <code>touchstart</code> event. This behavior is implemented by the <code>FastButton</code> class and described there. See class: <a href="{{ site.baseurl }}/ubuntu-html5-theme/other-apis/fastbutton/">FastButton</a>.


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

![Ubuntu HTML5 header]({{ site.baseurl }}/images/buttonsStyles.png)
