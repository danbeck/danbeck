---
layout: post
title:  "RamSamSam Reader: version 0.2.1 is live!"
date:   2013-09-15 11:00:00
categories: Ubuntu App Showdown, ramsamsam reader
---

Just in time for the Ubuntu App Showdown deadline, I released RamSamSam Reader version 0.2.1 in the click store. 

Many thinks were improved in version 0.2.1:


<h1>Offline reading</h1>
Articles are saved in the localstorage and can be read offline. To save space, images are not saved in the localstorage.

<h1>New UI element: number of unread items</h1>
Version 0.2.1 of RamSamSam Reader shows the number of unread items of a feed. Here is a screenshot of it, as it looks like on tablets. 

[caption id="attachment_1004" align="alignnone" width="831"]<a href="http://daniel-beck.org/wp-content/uploads/unreadItems-tablets1.png"><img src="http://daniel-beck.org/wp-content/uploads/unreadItems-tablets1.png" alt="Unread items (tablets)" width="831" height="769" class="size-full wp-image-1004" /></a> Unread items (tablets)[/caption]

<h1>Searching for newsfeeds</h1>
Entering an URL is quite unpractical on a phone. RamSamSam Reader can now search for RSS feeds. Simply enter one or several keywords in the "Add feed" dialog, and the google search is executed. URL and ebay-feeds work, too. At the end of this blog post is a video, that shows this feature in action.

<h1>Dynamic convergence</h1>
I implemented convergence dynamically. Depending on the resolution, 
<ol>
<li>the layout of the application changes, and</li>
<li>more pages are displayed on smaller displays</li>
</ol>

Point "2" means that the user is guided differently according to its display resolution. This provides a much better user experience. Technically, this means that the page-history has to be cleared, otherwise the back button would stop working. This feature made it in version 0.2.1, too. I named it "dynamic convergence" since it allows to switch the display mode at runtime (for example by rotating a smartphone in landscape mode).

<h1>TheOldReader: Cloud synchronization runs in the background</h1>
News items from theOldreader are downloaded in the background and stored in the localstorage.
As a result, using theOldReader-cloud feels <strong>*much*</strong> faster. Since data is loaded from the localstorage, clicking on a feed immediatly shows up its items. Try it out yourself!

<h1>TheOldReader: read articles</h1>
Articles are marked as read in the theOldReader-cloud as soon as they are displayed.



<h1>Simultaneous Android Release</h1>
Only a small amount of users could already install Ubuntu Touch on their handheld device. That's why I also released a <a href="http://daniel-beck.org/rss/RamSamSamReader-0.2.1.apk">binary of version 0.2.1 for Android</a>. Minimum requirement is Android version 4.1. 

<h1>Desktop version</h1>
Beeing programmed with HTML5 and javascript, RamSamSam Reader can also be tried without installation on a desktop computer. To use the synchronization feature with theOldReader, "chrome" must be started with " chromium-browser --disable-web-security". Firefox does not allow disabling CORS security checks and will thus only work with feeds stored locally.

Here is the link to the <a href="http://daniel-beck.org/rss">web version</a>.

<h1>Showcase video</h1>
Finally, for all users who do not want to install RamSamSam Reader, I created a showcase video where I show it in action.


http://www.youtube.com/watch?v=GFq7sBcb24Y&feature=youtu.be