---
layout: post
title:  "RamSamSam Reader: Synchronization with theOldReader"
date:   2013-09-05 17:25:00
categories: Ubuntu App Showdown
---

RamSamSam Reader can now connect and synchronize with <a href="http://theoldreader.com/">theOldReader</a>!

![The Old Reader]({{ site.baseurl }}/images/logo-landing.png)

In detail, the following data are synchronized:

- User Login
- Subscriptions
- Subscription tags (categories)
- Subscription icons
- Article contents
- Marking articles as read (synchronized in both ways)

It is possible to try this feature on the desktop by starting chrome with the flag "--disable-web-security". This allows chrome to make cross-domain HTTP requests to connect to theOldReader. This feature will <b>not</b> work with firefox, since firefox has no switch to disable the cross-domain HTTP policy. Here is the url where RamSamSam Reader can be tried out: <a href="http://daniel-beck.org/rss">http://daniel-beck.org/rss</a>.

The servers from theOldReader are rather slow, however <a href="https://twitter.com/jenbshaw/status/372914880950444033">theOldReader-team is aware of it</a> and tries to improve the performance problem. The user interface of RamSamSam Reader is asynchronous so that the user interface even responsiv when the webservice of theOldReader is slow.

One technical note: I kept the logic to retrieve the feeds separated from the interaction with the application logic and the user interface logic. I use a generic feed-datastructure, so that integrating other cloud-services essentially means implementing an interface which converts feeds to this data-structure. <strong>This lays the ground for other synchronization-connectors like "feedly", "Tiny Tiny RSS" and "Feedbin".</strong>

I will create click packages and android packages of RamSamSam Reader in the coming days.