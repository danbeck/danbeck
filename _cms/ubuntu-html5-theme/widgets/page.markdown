---
layout: post
title:  Page
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---
<h2>Overview</h2>

Pages are contained in a <a href="{{ site.baseurl }}/ubuntu-html5-theme/widgets/pagestack/"><code>pagestack</code></a>. The pagestack contains methods to show and hide pages.

<h2>Markup declaration</h2>

Pages must have the attribute <code>data-role="page"</code>. Here is an example:

```html
<div id="firstPage" data-role="page">
</div>
```


Pages can also contain a <a href="{{ site.baseurl }}/ubuntu-html5-theme/widgets/toolbar/">toolbar</a>:

```html
<div id="secondPage" data-role="page">
  <footer data-role="footer"></footer>
</div>
```
