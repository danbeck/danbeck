---
layout: post
title:  "MySQL: Creating a user and granting rights"
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---

<h2>Overview</h2>

The <a href="http://design.ubuntu.com/apps/building-blocks/header">header</a> is an UI component which sits at the top of an application. It usually contains a <a href="http://design.ubuntu.com/apps/building-blocks/tabs">tabs</a> container widget.

Here is a screenshot of such a header UI element:

[caption id="attachment_1215" align="alignnone" width="333"]<a href="http://daniel-beck.org/wp-content/uploads/Header.png"><img src="http://daniel-beck.org/wp-content/uploads/Header.png" alt="Header" width="333" height="71" class="size-full wp-image-1215" /></a> Header[/caption]

<h2>Markup declaration</h2>

Here is explanatory code snippet:

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