---
layout: post
title:  Text Input
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---

<h2>Overview</h2>
To make text input elements look like their native Ubuntu Touch counterparts, no special CSS classes are needed: the CSS rules directly match the attribute _type_ of the_&lt,input&gt;_ elements.

<h2>Markup declaration</h2>

Here is an example that declares text inputs with different input types:

```html
<div class="inset">
  <input type="text" placeholder="simple text field">
</div>
<div class="inset">
  <input type="text" disabled="" placeholder="disabled text field">
</div>
<div class="inset">
  <input type="tel" placeholder="telephone field">
</div>
<div class="inset">
  <input type="search" placeholder="search field">
</div>
<div class="inset">
  <input type="number" placeholder="number field">
</div>
<div class="inset">
  <input type="url" placeholder="url field">
</div>
<div class="inset">
  <input type="password" placeholder="password with echo">
</div>
<div class="inset">
  <textarea placeholder="the placeholder text is a text which is displayed when there is no content in the TextArea"></textarea>
</div>
```

The markup above produces the following in the webbrowser:

![Ubuntu HTML5 Text input]({{ site.baseurl }}/images/TextInputs.png)

