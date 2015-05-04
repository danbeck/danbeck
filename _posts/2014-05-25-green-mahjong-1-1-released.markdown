---
layout: post
title:  Green Mahjong 1.1 released
date:   2014-05-25 09:37:00
categories: Green Mahjong
---
Green Mahjong 1.1 was released today. The changes are numerous. Version 1.1 fixes many bugs, is themable, has an adaptive resolution (convergence) and is much faster. 

"A picture is worth a thousand words". Here is the screenshot of the new theme "fruits":
<a href="http://daniel-beck.org/wp-content/uploads/2014/05/GreenMahjongFruits.png"><img src="http://daniel-beck.org/wp-content/uploads/2014/05/GreenMahjongFruits.png" alt="GreenMahjongFruits" width="703" height="508" class="alignnone size-full wp-image-1964" /></a>

And here a screenshot of the theme "classic":

<a href="http://daniel-beck.org/wp-content/uploads/2014/05/GreenMahjongClassic.png"><img src="http://daniel-beck.org/wp-content/uploads/2014/05/GreenMahjongClassic.png" alt="GreenMahjongClassic" width="708" height="509" class="alignnone size-full wp-image-1967" /></a>

Here is the detailed changelog:

 * On Ubuntu Touch, Oxyde is used instead of Webkit/Ubuntu Cordova. This fixes a problem in version 1.0 where the game was only displayed in the upper quarter of the screen. 
 * Green Mahjong chooses the highest resolution game sprites possible for the used screen size. Four different sprite resolutions are available. Thus, everythink looks nice on the desktop, on a 10 inch tablet and on smaller smartphones. This even works at runtime, e.g. when resizing the browser on a desktop computer! 
 *  Because of the adaptive resolution, the app "Green Mahjong High Resolution" is not needed anymore in the Ubuntu Click store  and was removed
 * Themes! Two different theme sets are delivered: classic and fruits.
 * a big performance boost: version 1.0 used CSS3 shadows to archieve a more enjoyable look. However, CSS shadows are very slow and drawing the game quite slow. We archieved a 20x performance boost by predrawing the shadows as PNG pictures.
 * new background pictures
 * a new nice looking menu toolbar
 * a new game icon
 * the artwork is released under the creative common non commercial license

Here is the link to the project Git repository:
https://gitorious.org/green-mahjong/

We release the game tiles under the CC BY-NC license. Here is the link: <a href="http://daniel-beck.org/greenmahjong/mahjongfruit.svg">SVG tiles</a>.

Finally, the game can be tried out in the browser, too: <a href="http://daniel-beck.org/greenmahjong/">Green Mahjong</a>

Have fun!