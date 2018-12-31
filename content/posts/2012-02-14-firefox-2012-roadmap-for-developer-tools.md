---
title: Firefox 2012 Roadmap for Developer Tools
author: Kevin Dangoor
type: post
date: 2012-02-14T18:56:56+00:00
url: /2012/02/14/firefox-2012-roadmap-for-developer-tools/
categories:
  - Mozilla

---
# Firefox in 2012 {#firefox_in_2012}

This week, the [Firefox 2012 Roadmaps][1] went live. Mozilla has a lot going on and _huge_ goals for 2012. We have a lot to do and the web will be in a better place as a result.

## Developer Tools in 2012 {#developer_tools_in_2012}

It&#8217;s been two months since I posted the [2012 developer tools roadmap][2]. I thought that the new attention on the larger Firefox roadmap gives me a good opportunity to reflect on where developer tools is now and what&#8217;s coming in this year.

I want to start by saying that I think the Firefox developer tools team is doing amazing work. They&#8217;re shipping big features, great refinements and handling the growth of the community well.

This year, we&#8217;re filling in a new set of **bundled tools for the most common web development tasks**. Two weeks ago, we had our first big release of the year. I&#8217;ve been watching the feedback in various channels and it has been _overwhelmingly positive_. People have seen that we&#8217;re offering:

  * Streamlined user interfaces on&#8230;
  * Fast and well-tested tools that&#8230;
  * Meet the common needs in new and better ways

I really appreciate all of the constructive criticism we&#8217;ve gotten. Ryan DeBeasi wrote in [&#8220;New Developer Tools in Firefox 10 and 11&#8221;][3] for Web Designer Depot:

> There’s no user agent switcher, no “edit as HTML feature,” no performance-testing tools, no way to inject new tags into a page, no way to activate an element’s hover state. There’s not even a “layout” panel for viewing the dimensions, padding, and margins of your element.
> 
> Despite all those limitations, I keep coming back to the Page and Style Inspectors. I come back for the uncluttered interface, the thoughtfully placed panes, and that funky purple chrome. I come back because they’re a pleasure to use, and because they meet my needs most of the time.

Yep! That&#8217;s all true. And Tyler Herman&#8217;s recent [Impression of Firefox&#8217;s New Developer Tools][4] offered similar sorts of feedback. Those two articles are representative of much of the reaction I&#8217;ve seen surrounding Firefox 10&#8217;s release.

We&#8217;re happy that you think we&#8217;re off to a good start. We know we&#8217;ve got more work to do, and we&#8217;re listening. In the coming months, watch for new tools and improvements to the ones we&#8217;ve shipped.

Along those lines, a [huge chunk of work for the new JavaScript debugger][5] has recently made it into Nightly. It needs some more work before it&#8217;s usable and shippable, but the debugger is coming. As Panos mentions in that blog post, this debugger builds on entirely new infrastructure. More on that in a moment.

## Mobile {#mobile}

Mobile is huge in Mozilla&#8217;s roadmap for 2012. We&#8217;re working to ship a new [Firefox for Android][6] with a screaming fast native UI. The [Boot2Gecko project][7] is working on an entirely new mobile phone OS that is truly open source from top to bottom and from the very beginning of the project. Plus, B2G is open web all the way.

Our focus in developer tools is on tools that live in the desktop browser for the common web development cases. That doesn&#8217;t mean we&#8217;re not _thinking_ about mobile. We don&#8217;t think that people want to do mobile phone development on their mobile phones, hence the need for great desktop tools. Tablets are another story, but we still think that desktop OSes will rule development for some time to come.

The new debugger that I mentioned is built around a client/server architecture. In other words, an app running on in Firefox for Android could be debugged by a desktop Firefox browser. There are [infrastructure changes underway in the Web Console][8] that will help make remote access possible in the Web Console as well. We need to do non-trivial user interface work to expose this kind of feature, but the technical underpinnings are falling into place.

There&#8217;s another option that works especially well for Firefox: making the desktop browser _pretend_ to be a mobile device. Firefox on the desktop and Firefox for Android generally follow the same release schedules and rely on the same rendering engine, which means that the desktop should be able to behave quite closely to the way the mobile device does. Again, there&#8217;s work to be done before we can ship this and that work depends on us having our core desktop tools fleshed out.

## Apps and Add-ons {#apps_and_add_ons}

From the perspective of the code a developer creates, [Mozilla&#8217;s &#8220;Apps&#8221; initiative][9] is not all that different from standard web development. Apps use the latest web specs and have a little bit of wrapping around them. But, Mozilla is working to build a whole bunch of infrastructure around Apps to make the end-to-end user experience fantastic.

The tools that we&#8217;re building for web developers should be immediately applicable to Apps. Beyond those tools, though, providing the best possible end-to-end _developer experience_ for Apps developers is something we&#8217;d like to pursue.

Similarly, Firefox Add-ons built with the [Add-on SDK][10] are mostly built from the same kinds of technology web apps are built. Ideally, the tools that developers can use for the web could also be applied for Add-ons.

Daniel Buchner now reports to me as the product manager for Apps and Add-ons Developer Tools. He&#8217;ll be helping to identify the best opportunities we have in these areas.

## Firebug {#firebug}

I also wanted to give a shoutout to the splendid work coming out from the Firebug team. [Firebug 1.10][11] (currently in alpha) is going to be the first ever _restartless_ version of Firebug. The code organization changes that they&#8217;re making will make Firebug an even easier project to contribute to than it has been in the past. And, of course, new user-facing features are part of 1.10 as well.

## Many ways to get involved {#many_ways_to_get_involved}

Everything we do at Mozilla is open source and for the betterment of the web. Those of us working on developer tools at Mozilla want to make web development easier and more fun. You can help in a variety of ways:

  * Run [Firefox Aurora][12]. Aurora is two releases up from the current Firefox release. In my experience, Aurora is _remarkably stable_. By running Aurora, you get a sneak preview of coming features _and_ a chance to help us spot minor irritations before they go out the door.
  * Give us feedback! Feedback helps guide us, and we love to hear from web developers. 
      * Hit the feedback button on the toolbar of Firefox test releases (Aurora and Beta).
      * [email dev-apps-firefox][13],
      * [join the weekly meeting][14],
      * [talk to us on IRC][15],
      * [email me][16],
      * [send me a tweet (@dangoor)][17]
      * [plus me (is that a thing?)][18].
      * It doesn&#8217;t matter how. Just get in touch.
  * Blog your feedback. If you can fit your thoughts in 140 characters, go for it. Apparently, I&#8217;m too verbose for that!
  * Show off cool stuff. Like [a little city that magically appears in the Page Inspector 3D view][19] (you&#8217;ll need Firefox Beta for that).
  * [File bugs][20]
  * Pick up a &#8220;Good First Bug&#8221; or otherwise [get involved in the code][21]

I hope you enjoy the new tools in Firefox 10 and beyond. They&#8217;re just the beginning of [what we have planned for 2012][2].

 [1]: https://wiki.mozilla.org/Roadmaps
 [2]: https://wiki.mozilla.org/DevTools/RoadmapDec2011
 [3]: http://www.webdesignerdepot.com/2012/01/new-developer-tools-in-firefox-10-and-11/
 [4]: http://couchable.co/blog/post/impression-of-firefoxs-new-developer-tools
 [5]: http://blog.astithas.com/2012/02/debugging-javascript.html
 [6]: http://www.mozilla.org/en-US/mobile/
 [7]: https://wiki.mozilla.org/B2G/Roadmap
 [8]: https://bugzilla.mozilla.org/show_bug.cgi?id=673148
 [9]: https://wiki.mozilla.org/Apps/Roadmap
 [10]: https://addons.mozilla.org/en-uS/developers/builder
 [11]: http://blog.getfirebug.com/2012/02/10/firebug-1-10a3/
 [12]: http://mozilla.org/aurora
 [13]: https://lists.mozilla.org/listinfo/dev-apps-firefox
 [14]: https://wiki.mozilla.org/DevTools
 [15]: irc://irc.mozilla.org/#devtools
 [16]: mailto:kdangoor@mozilla.com
 [17]: http://twitter.com/dangoor
 [18]: https://plus.google.com/113027790166600260439/posts
 [19]: http://www.dev-kitchen.com/ff3d/
 [20]: https://bugzilla.mozilla.org/enter_bug.cgi?product=Firefox&component=Developer%20Tools
 [21]: https://wiki.mozilla.org/DevTools/GetInvolved