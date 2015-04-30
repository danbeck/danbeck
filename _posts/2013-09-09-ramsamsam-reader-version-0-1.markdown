---
layout: post
title:  "RamSamSam Reader: version 0.1.3 is Live!"
date:   2013-09-09 22:42:00
categories: Ubuntu App Showdown, ramsamsam reader
---

I uploaded the <a href="https://myapps.developer.ubuntu.com/dev/click-apps/43/">first click package of RamSamSam Reader</a> in the click-store. I'm really looking forward to get feedback from people who have installed Ubuntu touch on their smartphone.

As a side notice, I recommend everyone participating in the ubuntu touch showdown to upload its first version soon, since creating and uploading a click package is a very involving process. The click-store and the utilities to create the packages still have bugs and limitations.

Now, to the new version:
<h1>New and noteworthy</h1>
<h2>Day/night mode</h2>
If you surf at night, you know a regular white web page can hurt your eyes. The configuration-item "use night-mode" changes the theme of RamSamSam Reader to use dark colors.

Here is how this function looks like:

<a href="http://daniel-beck.org/wp-content/uploads/night.gif"><img class="alignnone size-full wp-image-773" alt="night" src="http://daniel-beck.org/wp-content/uploads/night.gif" width="800" height="510" /></a>

<h2>Adding Ebay searches as RSS Feeds</h2>
Ebay searches can be added to RamSamSam Reader. The application detects that this is an ebay URL and retrieves a RSS feed instead. This should at least work for ebay.de, ebay.fr and ebay.com. I believe that RamSamSam Reader is the first feed reader to have this feature.

<h2>Synchronization with "theOldReader"</h2>
The synchronization with theOldReader got many fixes and should be faster now. The synchronization is better integrated into RamSamSam Reader. It starts to download subscriptions as soon as the software starts.

<h2>Hiding the toolbar</h2>
As suggested in the <a href="http://design.ubuntu.com/apps/building-blocks/toolbar">design guidelines</a>, the toolbar should be hidden when the user touches it. This feature is now in version 0.1.3!

<h2>Configuration page</h2>
There is a new UI element to quickly access configuration items which are frequently needed: the configuration popover menu. For the moment, this menu allows to activate the night mode. In the future, it will offer other options like “change the sorting direction”, “only show unread items”, etc.

From the popover menu, the “extended configuration page” can be accessed, too. Here, further configurations can be found, like configuring the connection to theOldReader.

<table><tr><td>
[caption id="attachment_779" align="alignnone" width="179"]<a href="http://daniel-beck.org/wp-content/uploads/popupmenu.png"><img class="size-medium wp-image-779" alt="Popup menu" src="http://daniel-beck.org/wp-content/uploads/popupmenu-179x300.png" width="179" height="300" /></a> Popup menu[/caption]
</td><td>
[caption id="attachment_780" align="alignnone" width="183"]<a href="http://daniel-beck.org/wp-content/uploads/configurationmenu.png"><img class="size-medium wp-image-780" alt="Configuration page" src="http://daniel-beck.org/wp-content/uploads/configurationmenu-183x300.png" width="183" height="300" /></a> Configuration page[/caption]</td></table>

<h2>Scrolling</h2>
Unfortunately, <a href="https://bugs.launchpad.net/cordova-ubuntu/+bug/1222409">QtWebkit</a> has a bug: it is not possible to have two scrolling div-containers on the same page. This forced me to change version 0.1.3 so that scrolling the subscription also scrolls the subscription items. This is unfortunate, and I hope that the Ubuntu Touch team quickly fixes that, so that I can reestablish the old behavior.