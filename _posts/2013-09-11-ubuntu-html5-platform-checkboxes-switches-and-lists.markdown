---
layout: post
title:  "Ubuntu HTML5 platform: checkboxes, switches and lists"
date:   2013-09-11 19:55:00
categories: Ubuntu HTML5
---
In the last two articles (<a href="<a href=">first article</a> and <a href="http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-3/">second article</a>), we presented the Ubuntu HTML5 widgets <a href="http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-2#pagestack">pagestacks</a>, <a href="http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-2#pagestack">pages</a>, <a href=http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-2#backbutton">the backbutton</a>, <a href="http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-3#buttons">buttons</a>, <a href="http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-3#dialogs">dialogs</a>, and <a href="http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-3#sliders">sliders</a>. We continue our journey and look at "checkboxes", "switches" and "lists".

<h1>Toogles</h1>
<a href="http://design.ubuntu.com/apps/building-blocks/toggles">Toggles</a> are user interface elements which can be turned on and off. They can either be "checkboxes" or "switches".

<h2>Checkboxes</h2>
Checkbox are <input> HTML elements having the attribute <code>type="checkbox"</code>. Additionally, they can have two attributes:

 * checked: displays the checkbox as "checked"
 * disabled: disables the checkbox so that its state cannot be changed

This <input> element must be followed by an empty "<span>"-element. CSS stylessheets from the Ubuntu HTML5 Theme need this element to set a background image. Here is a code snippet which displays a checkbox:

```html
<div><label>
  <input type="checkbox" checked="checked" />
  <span></span>
</label>

<label>
  <input type="checkbox" /> <span></span>
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
</pre>

With Ubuntu HTML5 Theme, this HTML markup looks like this (from left to right: checked, unchecked, disabled and checked, disabled and unchecked):

[caption id="attachment_805" width="270"]<a href="http://daniel-beck.org/wp-content/uploads/Checkboxes.png"><img class="size-full wp-image-805" alt="Checkboxes" src="http://daniel-beck.org/wp-content/uploads/Checkboxes.png" width="270" height="35" /></a> Checkboxes[/caption]

Checkboxes have no predefined Javascript methods in Ubuntu HTML5. Accessing the state of the checkbox - checked or not checked - must be done with regular Javascript DOM-methods instead:


```html
<label>
  <input id="checkbox" type="checkbox" checked="disabled" />
</label>
<script>
var checkBoxState = true;
document.getElementById("checkbox").onclick = function(){
  checkBoxState = !checkBoxState;
}
</script>
```


<h2>Switches</h2>

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

<h1>List</h1>

Lists are predefined widgets that mostly look like their <a href="http://design.ubuntu.com/apps/building-blocks/list-items">native counterparts</a>. A container is declared as a list by setting the attribute <code>data-role="list"</code>. Lists consist of an <ul> element, containing <li> elements (i.e. list items). 

The following code declares a list consisting of two list items:

```html
<section data-role="list">
  <ul>
    <li>
      <p>Label</p>
    </li>
    <li>
      <p>Label</p>
      <p>Secondary Label</p>
    </li>
  </ul>
</section>  
```

This creates the following user interface:
[caption id="attachment_862" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/SimpleList.png"><img src="http://daniel-beck.org/wp-content/uploads/SimpleList.png" alt="A list containing two items" width="302" height="110" class="size-full wp-image-862" /></a> A list containing two items[/caption]

List items can also contain <header>-elements. Ubuntu HTML5 styles them smaller then normal list elements:

```html
<section data-role="list">
  <header>Header</header>
  <ul>
    <li>
      <p>Label</p>
    </li>
  </ul>
</section>  
```

Here is a screenshot of a header element and a "normal" list element:
[caption id="attachment_844" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/HeaderWithListItem.png"><img src="http://daniel-beck.org/wp-content/uploads/HeaderWithListItem.png" alt="A list made of a header and a normal list item" width="302" height="92" class="size-full wp-image-844" /></a> A list made of a header and a normal list item[/caption]


To give the user the illusion of "progression", list items can be designed to have an arrow on the right side. This is realized by surrounding a list-item with an <a>-element:

```html
<section data-role="list">
  <header>Header</header>
  <ul>
    <li>
      <a href="#">
        <p>Open this item</p>
      </a>
    </li>
  </ul>
</section>  
```

 [caption id="attachment_846" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/ListProgression.png"><img src="http://daniel-beck.org/wp-content/uploads/ListProgression.png" alt="List with a progression item" width="302" height="88" class="size-full wp-image-846" /></a> List with a progression item[/caption]

List items can have an icon on the left side:

```html
<section data-role="list">
  <header>Header</header>
  <ul>
    <li>
      <aside>
        <img src="../../ambiance/img/avatar_contacts_list@8.png" alt="placeholder">
      </aside>
      <p>Label</p>
    </li>
  </ul>
</section>
```

[caption id="attachment_847" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/LabelListItem.png"><img src="http://daniel-beck.org/wp-content/uploads/LabelListItem.png" alt="List item with a label" width="302" height="65" class="size-full wp-image-847" /></a> List item with a label[/caption]

However, this <aside> element has a very high z-index. It interfers with other Ubuntu HTML5 components like the toolbar: icons are visible behind the toolbar. There is a <a href="https://bugs.launchpad.net/ubuntu-html5-theme/+bug/1223973">bug report</a> for this.
Meanwhile, I recommand to overwrite the z-index like that:
```html
[data-role="list"] aside {
    z-index: 2;
}
```

List items can also contain switches and checkboxes:

```html
<section data-role="list">
  <header>This is a header</header>
  <ul>
    <li>
      <p>Switch</p>
        <label>
          <input type="checkbox" checked="" data-type="switch">
            <span class="toggle">
              <span class="toggle-handle"></span>
              <span class="toggle-bg"></span>
            </span>
        </label>
     </li>
    <li>
      <p>Checkbox</p>
      <label>
        <input type="checkbox">
        <span></span>
      </label>
    </li>
  </ul>
</section>
```

[caption id="attachment_849" align="alignnone" width="302"]<a href="http://daniel-beck.org/wp-content/uploads/CheckboxAndSwithMenuItems.png"><img src="http://daniel-beck.org/wp-content/uploads/CheckboxAndSwithMenuItems.png" alt="Checkbox and switch menu items" width="302" height="117" class="size-full wp-image-849" /></a> Checkbox and switch menu items[/caption]

Ubuntu HTML5 theme delivers a convenient javascript API to access and manipulate lists.

<code>append(text, label, id, onclick, data)</code> creates a new list item and appends it to the end of a list.  This method only needs to be called with the <code>text</code> argument, all other arguments are optional. <code>text</code> is displayed on the left side of the created list element, <code>label</code> is normally used to show an image or a toggle, it is displayed on the right side. With "id" the list element gets assigned an "id"-attribute. A click event-handler can be passed with <code>onclick</code>. <code>data</code> allows to pass supplementary data to the event-handler.

This code adds several list items to an existing list:

```javascript
UI.list('somelist').append("The"); 
UI.list('somelist').append("answer"); 
UI.list('somelist').append("is"); 
UI.list('somelist').append("42");
```


The following example adds the list item "startwifi" to a list named "actions". When a user clicks on it, a wifi connection is opened by using the provided username and password:

```javascript
var wifiConfig = {username: "admin", password: "secret"};
UI.list('actions').append("Start Wifi", null, function(wifiData){
   // start wifi
}, wifiConfig);
```

The following methods allow accessing and removing elements from a list:

* <code>at(n)</code>: accesses the n-th element of the list. Returns a <li> element
* <code>remove(n)</code>: removes the n-th element of the list
*<code>removeAllItems()</code>: removes all items of a list

Finally, there is also a <code>forEach()</code> method which iterates over all list items and applies a function to them. This could for example be used to assign a CSS class named "odd" to each second item:

```javascript
UI.list('list').forEach(function(element, index) {
   if(index % 2 === 1)
      element.classList.add("odd");
});
```

This closes the description of checkboxes, switches and lists. The next article will look at the toolbar and  popover menus.