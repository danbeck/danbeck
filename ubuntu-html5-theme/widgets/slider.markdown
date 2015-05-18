---
layout: post
title:  Slider
date:   2010-07-09 09:03:00
categories: Ubuntu HTML5 theme
---

<h2>Overview</h2>
Sliders have a single handle that can be moved horizontally with the mouse or the touch screen. 

<h2>Markup declaration</h2>
They are declared in the HTML markup as follows:

```html
<input id="myslider" type="range" value="0" max="100" min="0" name="formvalue"&gt;
```

Additionally, the result of the selected value can be shown in an output-field like this:

```html
<form onsubmit="return false" oninput="displayedAge.value = age.valueAsNumber"&gt;
  <input name="age" id="age" type="range" min="0" max="100" value="0"&gt;
  <output for="age" name="displayedAge"&gt;0</output&gt;
</form>
```

Using a slider with an output element looks like this:

<a href="http://daniel-beck.org/wp-content/uploads/slider.png"><img class="size-full wp-image-710" alt="A slider" src="http://daniel-beck.org/wp-content/uploads/slider.png" width="234" height="49" /></a>