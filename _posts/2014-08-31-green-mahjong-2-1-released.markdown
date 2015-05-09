---
layout: post
title:  Green Mahjong 2.1 released!
date:   2014-08-31 07:52:00
categories: Green Mahjong
---
Green Mahjong 2.1 includes many improvements. 

New layouts
-----------

We added two board layouts: "bug" and "four hills":

![Greenmahjong: new themes]({{ site.baseurl }}/images/layouts_big.png)


Game statistics, points and achievement system
----------------------------------------------

Green Mahjong 2.1 introduces points. Solving a board gives you a bonus. There is also a
time bonus for solving a game under 8 minutes. Points and achievements are shown at the 
end of a game:


![Greenmahjong: game statistics]({{ site.baseurl }}/images/Bildschirmfoto-am-2014-08-07-um-21.13.37.png)

New menu
---------
The old menu appeared and disappeared when the player touched the background. This maximized the available screen estate, 
which is a nice thing since there is not a lot of space available on a phone. However, sometimes it also got in the way while 
playing. 

The new game menu is much more userfriendly and doesn't cost much more screen estate: 

![Greenmahjong hints: before/after]({{ site.baseurl }}/images/newMenu.png)
            
            
Improved visuals: hints
------------------------


The improved hint function is much faster on slower devices. It also looks better.
In the preceding version, we used CSS filters to grey out the blocked tiles. We now hand created grey tiles.
IMO, the result looks much better and can be discerned more clearly:

![Greenmahjong hints: before/after]({{ site.baseurl }}/images/hints.png)


<strong>Many speed improvements on old devices</strong>

 * much less dom manipulation
 * hints are realized with sprites instead of CSS filter

The game can be played in the browser, too: <a href="http://greenmahjong.daniel-beck.org"><strong>Green Mahjong</strong></a>

Have fun! 
Give us a review in your favorite app store if you like the game!

