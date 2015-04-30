---
layout: post
title:  "Ubuntu HTML5 platform: introduction"
date:   2013-08-28 08:42:00
categories: Ubuntu HTML5
---

<h2>Introduction</h2>

The importance of HTML5 to develop mobile applications rises sharply. This is mainly due to the increased amount of mobile platforms and to the popularity of HTML5 amongst developers. So, it is not surprising that HTML5 is, together with native apps, a first class citizen of <a href="http://www.ubuntu.com/phone/ubuntu-for-android">Ubuntu Touch</a>.

These article series are aimed at Web-developers with basic HTML4.01, CSS and Javascript knowledge. Since HTML5 is still a very young technology, I will explain new HTML5 concepts whenever they appear. 

I will cover the following themes:

* <a href="taming-the-ubuntu-html5-platform-part1/">Apache Cordova and the Ubuntu HTML5 Theme</a>
* <a href="taming-the-ubuntu-html5-platform-part-2/">The Ubuntu HTML5 widgets (Part 1)</a>
* <a href="taming-the-ubuntu-html5-platform-part-3/">The Ubuntu HTML5 widgets (Part 2)</a>
* The Ubuntu HTML5 widgets (Part 3)
* The Ubuntu HTML5 widgets (Part 4)
* Making the application look and feel more "native"
* Convergence: make an application look good on tablets and on phones
* Testing the application and packaging it
* Making it run on other platforms too

<h2>Apache Cordova</h2>
To leverage the power of HTML5, Ubuntu Touch uses <a href="http://cordova.apache.org/">Apache Cordova</a>. Apache Cordova is a platform to develop mobile applications with HTML and Javascript, and supports - beside Ubuntu Touch - many platforms like "Android", "IPhone", "Windows 8" and even "Tizen".
Here is a description of Apache Cordova from the project homepage:

<blockquote>Apache Cordova is a set of device APIs that allow a mobile app developer to access native device function such as the camera or accelerometer from JavaScript.</blockquote>

Technically, bundling HTML5 as a mobile application is done by executing a WebView (e.g. a Webkit-widget) with a native application wrapper. The WebView shows one web page (named index.html by default) that references whatever CSS, JavaScript, images, media files, which are necessary for it to run. 

Javascript API for camera or accelerometer are included in Apache Cordova. They are implemented natively for each platform and can be accessed with a cross-platform wrapper API.  This makes it possible to develop an application for several mobile platforms.

<h2>Ubuntu HTML5 theme</h2> 
One of the main points of Apache Cordova is that it facilitates "cross-platform development" for mobile platforms. However, users don't want the user interface  to look and to behave the same on all platforms. Even on the same platform, the look and feel can change between versions. This was the case for example with Android 4.0 and will be the case with iOS 7.

For that, Apache Cordova is often used with UI frameworks such as jQuery Mobile, Dojo Mobile or Sencha Touch, that provide a near-native look and feel. In the case of Ubuntu Touch, the <a href="https://launchpad.net/ubuntu-html5-theme">Ubuntu HTML5 Theme</a> is used. The Ubuntu HTML5 Theme makes an Apache Cordova application almost look like a native Ubuntu applications. Its <a href="http://de.wikipedia.org/wiki/GNU_Lesser_General_Public_License">GNU LGPL v3</a> license allows it to be used in closed-source commercial applications, as long as the changes made to Ubuntu HTML5 Theme are redistributed under the same license.

I introduce the basics of the Ubuntu HTML5 Theme in the next article: <a href="http://daniel-beck.org/taming-the-ubuntu-html5-platform-part-2/">Part 2</a>.