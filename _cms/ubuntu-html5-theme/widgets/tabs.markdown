---
layout: post
title:  Tabs
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---
<h2>Overview</h2>

The <a href="http://design.ubuntu.com/apps/building-blocks/header">header</a> is an UI component which sits on top of an application.  It
<ul>
<li>shows to the user where he is </li>
<li>It contains tabs. Tabs are views of equal importance (see the <a href="http://design.ubuntu.com/apps/building-blocks/tabs">guidelines</a>)</li>
</ul>

Here is a screenshot of such a header UI element:


![Ubuntu HTML5 header]({{ site.baseurl }}/images/header.png)


<code>Tabs</code> is defined in the file <a href="file:///usr/share/ubuntu-html5-theme/0.1/ambiance/js/tabs.js">/usr/share/ubuntu-html5-theme/0.1/ambiance/js/tabs.js</a>


<h2>Markup declaration</h2>

Here is an explanatory code snippet:

```html
<header data-role="header">
  <nav class="tabs" data-role="navbar">
    <div class="tabs-inner">
      <ul data-role="tabs">
        <li class="active" data-role="tab">
          <a href="#item1" id="firstTab">First</a>
        </li>
        <li class="inactive" data-role="tab">
          <a href="#item2" id="secondTab">Second</a>
        </li>
      </ul>
    </div>
  </nav>
</header>
```


<h2>Javascript access method</h2>

```javascript
var UI = new UbuntuUI();
UI.init();
var tabs = UI.tabs('#tabId');
```

The <code>Tabs</code> container is created by passing a <code>selector</code> to <a href="http://daniel-beck.org/ubuntu-html5-theme/widgets/ubuntu-ui/">UbuntuUI.tabs(DOMString selector)</a>;

<h2>Interface definition</h2>
Currently, <code>Tabs</code> objects only have internal methods which should not be used by application programmers.
