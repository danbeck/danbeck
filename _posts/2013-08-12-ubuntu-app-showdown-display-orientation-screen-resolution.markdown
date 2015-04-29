---
layout: post
title:  "Ubuntu App Showdown: display orientation, screen resolution"
date:   2013-08-16 00:06:00
categories: Ubuntu App Showdown
---


Since I'm using HTML5 instead of QML, one of the challenges is make the RSS feed reader behave like a native application. One such challenge is to make the application adapt to orientation an screen size.

My RSS feed reader displays feeds differently depending on the handheld and how the handheld is held.

If the user uses a smartphone in portrait mode, the RSS feed reader looks like that:

[caption id="attachment_270" align="alignnone" width="160"]<a href="http://daniel-beck.org/wp-content/uploads/display-for-smartphone.png"><img class="size-medium wp-image-270" alt="Landscape mode smartphone" src="http://daniel-beck.org/wp-content/uploads/display-for-smartphone-160x300.png" width="160" height="300" /></a> Landscape mode smartphone[/caption]

If he uses his smartphone in landscape mode, the application reacts to this and displays two columns:

[caption id="attachment_271" align="alignnone" width="300"]<a href="http://daniel-beck.org/wp-content/uploads/display-for-smartphone-landscape.png"><img class="size-medium wp-image-271" alt="Smartphone - landscape mode" src="http://daniel-beck.org/wp-content/uploads/display-for-smartphone-landscape-300x133.png" width="300" height="133" /></a> Smartphone - landscape mode[/caption]

Finally, on handhelds having a resolution higher as 480px, the RSS feed reader looks like that:

[caption id="attachment_272" align="alignnone" width="300"]<a href="http://daniel-beck.org/wp-content/uploads/display-for-tablets.png"><img class="size-medium wp-image-272" alt="Tablet mode" src="http://daniel-beck.org/wp-content/uploads/display-for-tablets-300x245.png" width="300" height="245" /></a> Tablet mode[/caption]

The user will have the possibility to configure (and so overwrite the default behavior) in a later version of the software.