---
title: Tools for Web Developers (1DevDay)
author: Kevin Dangoor
type: post
date: 2011-11-11T00:46:24+00:00
url: /2011/11/10/tools-for-web-developers-1devday/
categories:
  - JavaScript

---
This past Saturday, I had the pleasure of speaking at [1DevDay Detroit 2011][1]. The event was held at the fantastic Compuware headquarters in downtown Detroit. It&#8217;s a beautiful building, and the training center facility works well for events like 1DevDay.

I spoke about &#8220;New Tools for the Open Web&#8221;. My goal was to show off a bunch of tools that people might find useful and to talk about tools for the future. It&#8217;s impossible to talk about all of the great stuff that&#8217;s going on. The world of open source tools for the web is huge and growing, and there was a standing-room-only crowd for my talk (thanks for packing in there and letting me run over my timeslot a little bit!)

I started with some tools that aren&#8217;t new, hopefully showing off some cool features along the way.

  * The [Web Developer Toolbar][2] has an incredible number of utilities packed into its menus. It&#8217;s not new, but it should be in your toolbox.
  * [Firebug][3] has had a huge influence on tools for web developers and continues to get awesome new features (such as more fields on the Net Panel and the ability to select which ones you want). I also pointed out Firebug&#8217;s non-standard but amazingly useful control for quickly selecting script files on the script page.
  * I spoke about a couple of neat JavaScript features in the Chrome Developer Tools (the ability to tweak JS on the fly and the ability to prettify JS while you&#8217;re debugging)
  * I showed off the Web Console and Scratchpad tools from Firefox, in particular showing how Scratchpad provides a very clean, usable interface for experimenting with JS.
  * I gave a sneak preview of the new Firefox styling tools that will very soon be in [Firefox Aurora][4] builds.
  * I showed of the Firefox style editor which should be in the next Aurora. For now, it&#8217;s available [as an add-on][5]
  * I also demoed [Tilt][6], an amazing 3D visualization of the DOM

In a category all its own is [Weinre][7] which provides a way to debug apps running on a mobile device.

Then, I stepped into a collection of CSS tools.

  * [ReCSS][8] is a bookmarklet that&#8217;s been available forever. One tap of the bookmarklet reloads your CSS without refreshing the page.
  * [LESS][9] extends the CSS language with a variety of useful features and compiles down to standard CSS to run in the browser. It&#8217;s written in JavaScript, so you can do the processing client side or server side. Neat trick: if you are doing client side processing, you can add #!watch to your URL and LESS will periodically refresh the CSS from the server automatically. Make a change on disk and see the change almost immediately in the browser. I also mentioned [Sass][10] and [Stylus][11] as alternatives.
  * [CSS Prefixer][12] helps you out by expanding your CSS3 declarations to work in all of the browsers that support them with a prefix (-moz, -webkit, etc.)
  * [Prefix Free][13] is an alternative to CSS Prefixer that works client side and adds only the declarations needed for the user&#8217;s browser.
  * [Rainbow][14] is a Firefox add-on for working with colors. Among its many neat features, it will give you the color palette for the page you&#8217;re looking at. The [Colour Bookmarklet][15] does something similar as a cross-browser bookmarklet.
  * [DOM Monster][16] is a cross-browser bookmarklet that will take a look at your page and give you specific advice on how to make it faster

I put out a call on Twitter and G+ for suggestions of tools that people rely on for their web development. Several cited their editors, so I thought I&#8217;d mention a couple.

  * [JSFiddle][17] takes the pastebin concept a couple of steps further by giving you a way to easily share snippets of HTML/CSS/JS that are put together into a preview pane. [JSBin][18] is an alternative
  * The [Eclipse Orion][19] project is building a browser-based IDE with workflows and plugins that feel very much &#8220;like the web&#8221;.We [ship the Orion text editor component][20] in Firefox
  * [Cloud9 IDE][21] provides a beautiful and feature-rich IDE for working on both the client and server parts of your application&#8230; all in the cloud!

I didn&#8217;t talk a whole lot about JavaScript-specific tools, because a lot of what we use for JS are libraries and not tools.

  * I showed [JSHint][22], a fork of Douglas Crockford&#8217;s ever-popular JSLint. JSHint provides nice static analysis of your JavaScript code to catch some errors early
  * [CoffeeScript][23] is a nice language that provides a friendlier syntax on top of JS without changing the semantics. This means that the JS it produces is quite readable (and quite close to what you&#8217;d write by hand). I&#8217;m still hoping that some of CoffeeScript&#8217;s best parts make it into ECMAScript.next (and there&#8217;s a good chance that a lot will).
  * Using a language like CoffeeScript makes debugging a bit harder. I showed off our not-quite-ready-yet [source maps][24] feature for Firefox. Source maps will also be really useful for debugging minified JavaScript.

I spoke a little about docs. Documentation is important, and the more we do to have better docs for our tools and libraries, the better.

  * I think [JQAPI][25] is awesome. They took the standard jQuery docs and reformatted them to be more useful.
  * [Docco][26] lets you do literate-style programming in JavaScript (or Python or any of the other ports that are available).
  * [Eloquent JavaScript][27] is a book that teaches you JavaScript and provides interactive exercises to help with the learning

Then, I spoke a bit about the future.

  * It always bears repeating: [anything you can do to help old browsers die is good for the web][28]
  * WYSIWYG tools can be nice, but HTML, CSS and JavaScript are quite reasonably hand-writable. Tools that assist in hand authoring provide the most power.
  * The mobile revolution needs more tools. And what will tools look like on modern tablets?
  * Have you seen [what a Smalltalk environment is like?][29]. More of that for the web, please 🙂
  * but not [actual Smalltalk][30]

**Almost everything I showed was created in HTML, CSS and JavaScript**. If you can make web apps, you can make tools. Even the tools that are built into the browsers are built of the same basic stuff.

Invest in your tools:

  * Find the good ones, use them and tell others!
  * Give feedback (this really helps people who make tools to make them better)
  * Make them better
  * Make entirely new ones

I mentioned how some tools, like Matthew Claypotch&#8217;s [localStorage bookmarklet][31] are very simple to write but can meet your needs precisely and even show toolmakers what you&#8217;d like to have.

Other tools mentioned to me by others but not part of my talk:

  * [Glimpse][32] is a client-side view into a server-side ASP.net applicaiton
  * [Edit This Cookie][33] is a Chrome extension for editing cookies. There&#8217;s also [Firecookie][34] for Firebug
  * [YSlow][35] is a tool from Yahoo! for spotting performance problems with your pages
  * [stat.js][36] is a bookmarklet that gives you information (such as frames per second) for the page you&#8217;re looking at
  * [h5o][37] provides an outline view for HTML5 documents
  * [LiveReload][38] automatically reloads your JS and CSS as you change it (oh, and it will recompile your CoffeeScript, Sass or LESS for you at the same time)
  * [ReloadEvery][39] is a Firefox extension to reload periodically automatically
  * [redbot][40] spots problems with the way you&#8217;re serving up your pages
  * [HttpFox][41] is a Firefox extension that provides an alternative view of network requests
  * [ColorZilla][42] is another set of color tools for Firefox
  * [Fiddler][43] is a web-debugging proxy

And there are many, many more. It&#8217;s a good time to be building web applications.

 [1]: http://1devdaydetroit.com/
 [2]: http://chrispederick.com/work/web-developer/
 [3]: http://getfirebug.com/
 [4]: http://www.mozilla.org/en-US/firefox/channel/
 [5]: http://neonux.com/StyleEditor/builds/
 [6]: https://addons.mozilla.org/en-US/firefox/addon/tilt/
 [7]: http://phonegap.github.com/weinre/
 [8]: http://david.dojotoolkit.org/recss.html
 [9]: http://lesscss.org
 [10]: http://sass-lang.com/
 [11]: http://learnboost.github.com/stylus/
 [12]: http://cssprefixer.appspot.com/
 [13]: http://mzl.la/prefixfree
 [14]: https://addons.mozilla.org/en-US/firefox/addon/rainbow-color-tools/
 [15]: http://wearepandr.com/labs/colour_bookmark
 [16]: http://mir.aculo.us/dom-monster/
 [17]: http://jsfiddle.net/
 [18]: http://jsbin.com
 [19]: http://www.eclipse.org/orion/
 [20]: http://planetorion.org/news/2011/11/orion-editor-ships-in-firefox-8/
 [21]: http://c9.io
 [22]: http://jshint.com
 [23]: http://jashkenas.github.com/coffee-script/
 [24]: http://www.youtube.com/watch?v=UAGAB-yT0lQ
 [25]: http://jqapi.com/
 [26]: http://jashkenas.github.com/docco/
 [27]: http://eloquentjavascript.net/
 [28]: http://paulirish.com/2011/browser-market-pollution-iex-is-the-new-ie6/
 [29]: http://vimeo.com/27850933
 [30]: http://amber-lang.net/
 [31]: http://potch.me/ls/
 [32]: http://getglimpse.com/
 [33]: https://chrome.google.com/webstore/detail/fngmhnnpilhplaeedifhccceomclgfbg
 [34]: https://addons.mozilla.org/en-US/firefox/addon/firecookie/
 [35]: http://developer.yahoo.com/yslow/
 [36]: http://ricardocabello.com/blog/post/707
 [37]: http://code.google.com/p/h5o/
 [38]: http://livereload.com/
 [39]: https://addons.mozilla.org/en-US/firefox/addon/reloadevery/
 [40]: http://redbot.org/
 [41]: https://addons.mozilla.org/en-US/firefox/addon/httpfox/
 [42]: https://addons.mozilla.org/en-US/firefox/addon/colorzilla/
 [43]: http://www.fiddler2.com/fiddler2/