---
title: r2d2b2g is becoming the Firefox OS Simulator!
author: Kevin Dangoor
type: post
date: 2012-11-08T16:28:04+00:00
url: /2012/11/08/r2d2b2g-is-becoming-the-firefox-os-simulator/
categories:
  - Mozilla

---
It&#8217;s been a month since Myk Melez posted an [introduction to r2d2b2g][1], a prototype Firefox add-on that makes it easy to try out [B2G][2] (Mozilla&#8217;s new, completely web platform-based mobile OS) on your desktop/laptop computer. Just as B2G is growing up to become [Firefox OS][3], r2d2b2g is growing up to become the Firefox OS Simulator.

The work of [Myk][4], [Harald][5] and [Matt][6] is coming along nicely, and you can try it out today by picking up Wednesday&#8217;s [r2d2b2g 0.6 release][7].

Quite a bit has changed since Myk&#8217;s blog post, so I&#8217;ll give a run through of the Simulator as it stands today. The biggest difference between the early r2d2b2g releases and the latest is that it is now much easier to install apps that you&#8217;re working on into the Simulator. Let&#8217;s take a look!

The Simulator has moved into the Web Developer menu.

[<img class="aligncenter size-medium wp-image-2980" title="Firefox OS Simulator in the menu" src="http://www.blueskyonmars.com/images/2012/11/Fullscreen-11812-1016-AM-300x257.png" alt="" width="300" height="257" srcset="https://www.blueskyonmars.com/images/2012/11/Fullscreen-11812-1016-AM-300x257.png 300w, https://www.blueskyonmars.com/images/2012/11/Fullscreen-11812-1016-AM.png 618w" sizes="(max-width: 300px) 100vw, 300px" />][8]

&nbsp;

The Simulator also integrates with the command line on the Developer Toolbar. Use the `firefoxos manager` command to jump into the Simulator Manager, just as the menu item does.

Here&#8217;s the Simulator Manager itself:

<p style="text-align: center;">
   <a href="http://www.blueskyonmars.com/images/2012/11/Firefox-OS-Simulator-Manager-0.6-3.png"><img class="aligncenter  wp-image-2981" title="Firefox OS Simulator Manager 0.6" src="http://www.blueskyonmars.com/images/2012/11/Firefox-OS-Simulator-Manager-0.6-3.png" alt="" width="702" height="283" srcset="https://www.blueskyonmars.com/images/2012/11/Firefox-OS-Simulator-Manager-0.6-3.png 877w, https://www.blueskyonmars.com/images/2012/11/Firefox-OS-Simulator-Manager-0.6-3-300x121.png 300w" sizes="(max-width: 702px) 100vw, 702px" /></a>
</p>

On the left, you&#8217;ll find some navigation controls including a switch that lets you start and stop the Simulator. The Simulator itself is still [B2G Desktop][9], which is a build of B2G that runs natively on Windows, Mac and Linux. You can also start and stop the Simulator using the `firefoxos start` and `firefoxos stop` commands in the Developer Toolbar. The &#8220;JS Console&#8221; checkbox allows you to start up B2G Desktop&#8217;s Error Console so that you can spot errors that might arise while you&#8217;re working on your apps.

In the screenshot above, you&#8217;ll see that I&#8217;ve already installed a couple of apps. You can add apps by providing a URL to a site (with autocompletion based on your open tabs) or, even better, a URL to a [manifest][10] (so that the app can have a proper icon and such). You&#8217;ll need a manifest file anyhow to submit to the [Firefox Marketplace][11], so you might as well start out with that early on.

You can also locate a manifest file on your local computer so that you can create a [packaged app][12] (no web server required!).

In the screenshot above, you&#8217;ll see that I installed James Long&#8217;s [Weather Me][13] app straight from GitHub and Fred Wenzel&#8217;s Serpent game from a local clone of its [git repository][14]. I&#8217;ll note that I did have to tweak the manifest for Serpent a little bit, because it was set up to deploy to GitHub rather than from its local directory. Changing just a couple of fields was all it took and then it worked great!

With those set up, I clicked the switch that says &#8220;Stopped&#8221; to fire up the Simulator. Then, I unlocked it with a swipe of the mouse, and swiped left on the home screen to get to my apps:

[<img class="aligncenter size-full wp-image-2982" title="Firefox OS Simulator" src="http://www.blueskyonmars.com/images/2012/11/11812-1046-AM-2.png" alt="" width="320" height="533" srcset="https://www.blueskyonmars.com/images/2012/11/11812-1046-AM-2.png 320w, https://www.blueskyonmars.com/images/2012/11/11812-1046-AM-2-180x300.png 180w" sizes="(max-width: 320px) 100vw, 320px" />][15]

As you can see, the Weather Me and Serpent apps are installed and ready for testing! One new feature I&#8217;d like to point out is the home button at the bottom of the Simulator. You no longer have to guess which key to press on your keyboard&#8230; just click the on-screen button as you would on a phone.

While hacking away on these apps, if I make changes I just have to follow some simple rules to see my changes. Hosted apps follow the usual rules for website caching and for working with appcache (which you should!). You can update packaged apps just by clicking the Update button in the dashboard and restarting the Simulator.

Once you&#8217;re done working with an app, you can remove it from the manager, which will also remove it from the Simulator (though you made need to restart your Simulator to see it disappear).

The Firefox OS Simulator is the easiest way to try out Firefox OS apps today and to verify how they&#8217;ll look before [submitting them to the Marketplace][16].

[Install it today][7] and [let us know if you run into any problems][17]. There are currently known issues on Windows XP and Linux that we&#8217;re working to resolve, but Windows 7 and Mac users should try it now!

 [1]: https://hacks.mozilla.org/2012/10/r2d2b2g-an-experimental-prototype-firefox-os-test-environment/
 [2]: https://wiki.mozilla.org/B2G
 [3]: http://mozilla.org/firefoxos/
 [4]: http://mykzilla.blogspot.com/
 [5]: https://twitter.com/digitarald
 [6]: http://twitter.com/tofumatt
 [7]: http://people.mozilla.org/~myk/r2d2b2g/
 [8]: http://www.blueskyonmars.com/images/2012/11/Fullscreen-11812-1016-AM.png
 [9]: https://developer.mozilla.org/en-US/docs/Mozilla/Boot_to_Gecko/Using_the_B2G_desktop_client
 [10]: https://marketplace.mozilla.org/developers/docs/manifests
 [11]: https://marketplace.mozilla.org/
 [12]: https://developer.mozilla.org/en-US/docs/Apps/Packaged_apps
 [13]: http://jlongster.github.com/weatherme/
 [14]: https://github.com/fwenzel/serpent/
 [15]: http://www.blueskyonmars.com/images/2012/11/11812-1046-AM-2.png
 [16]: https://marketplace.mozilla.org/developers/docs/mkt_submission
 [17]: https://github.com/mozilla/r2d2b2g/issues?state=open