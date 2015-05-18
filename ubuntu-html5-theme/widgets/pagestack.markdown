---
layout: post
title:  "Pagestack"
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---
<h2>Overview</h2>
Usually, Ubuntu HTML5 applications have one <code>Pagestack</code>. Pagestack manages <code>pages</code> with a stack data structure, hence the name of the class. A <code>pagestack</code> can contain a toolbar for all its pages, however, pages can also have their own toolbar.
The <code>pagestack</code> has methods to show and hide pages. Only one page and its toolbar can be displayed at the same time. Each time a page is shown, its global DOM id is added on the stack of pages. The <code>pop</code> method removes a page from the stack and shows the preceding page instead.


<code>Pagestack</code> is defined in the file <a href="file:///usr/share/ubuntu-html5-theme/0.1/ambiance/js/core.js">/usr/share/ubuntu-html5-theme/0.1/ambiance/js/pagestacks.js</a>

<h2>Markup declaration</h2>

This declares an empty pagestack containing no pages and no toolbar.
```html
<div data-role="pagestack">
</div>
```

The following markup declares a pagestack with a main footer for the whole pagestack. It contains two pages:
```html
<div data-role="pagestack">
  <div id="firstPage" data-role="page">
  </div>
  <div id="secondPage" data-role="page">
  </div>
  <footer data-role="footer"></footer>
</div>
```html

<h2>Javascript access method</h2>
Accessing the pagestack is made as follows:

```javascript
var UI = new UbuntuUI();
UI.init(); // initalizes the pagestack
var pagestack = UI.pagestack;
```

<h2>Interface definition</h2>

```javascript
interface Pagestack {
  void push(DOMString domId);
  DOMString pop();
  void clear();
  boolean isEmpty();
  DOMString currentPage();
  unsigned long depth();
};
```

<h2>Javascript access method</h2>

<dl>
<dt>void push(DOMString domId)</dt>
<dd>displays the page having the global id <code>domId</code> and its associated footer. All other pages are made invisible. Additionally, <code>domId</code> is added on the internal stack of pages maintained by the <code>pagestack</code> object.</dd>

<dt>DOMString pop()</dt>
<dd>hides the page which is actually shown, and removes it from the top of the internal stack of pages. Instead, the preceding page, which global id is now on the top of the stack, is shown. If the internal stack is empty, nothing happens.
</dd>

<dt>void clear()</dt>
<dd>makes all pages invisible and clears the internal stack of pages (used by the <code>push()</code> and and <code>pop()</code> methods).</dd>

<dt>boolean isEmpty()</dt>
<dd>returns <code>true</code> if the internal stack of pages is empty. Else, <code>false</code> is returned.

<dt>DOMString currentPage()</dt>
<dd>returns the global id of the currently displayed page. If no page is displayed (i.e. if the internal stack of pages is empty), <code>null</code> is returned.

<dt>unsigned long depth()</dt>
<dd>returns the size of the stack of pages.</dd>


</dl>
