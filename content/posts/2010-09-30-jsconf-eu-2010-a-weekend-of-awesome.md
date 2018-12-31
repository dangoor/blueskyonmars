---
title: 'JSConf.eu 2010: a weekend of awesome'
author: Kevin Dangoor
type: post
date: 2010-10-01T01:51:33+00:00
url: /2010/09/30/jsconf-eu-2010-a-weekend-of-awesome/
categories:
  - JavaScript
  - Mozilla

---
Last year, I was disappointed to have to cancel my trip to JSConf.eu. This year, my luck was better, and I spent this past weekend in Berlin, along with two of my Mozilla Developer Tools colleagues, [Joe Walker][1] and [Patrick Walton][2]. Mozilla was out in force at the conference. [Axel Hecht][3], who has been incredibly helpful bringing my team up to speed with localization, was in attendance. Oh yeah, and that guy from [A Minute With Brendan][4] was there. More seriously, I appreciated getting some good feedback from [Brendan][5] regarding where we&#8217;re heading with developer tools.

The conference organizers for JSConf.eu are fantastic, and I&#8217;ve got to thank Anja and Jan in particular for being exceedingly helpful. Jan even got us set up at [co.up][6], which is a really nice coworking space that was easily reachible from our hotel.

You&#8217;re probably wondering if I&#8217;m just going to blather on about people&#8230; What about the conference? Seriously, the talking to people is what a conference is all about. The talks are great, but the hallway track is also fantastic in a small conference of enthusiastic people like JSConf.

JSConf is one of those conferences where you feel like everyone around is smarter than you are but, thankfully, also approachable, friendly and wanting to share.

Among JSConf goers, at least, the presence of [Node][7] is huge now. Even [Peter Higgins][8] was forced to mention Node in his talk after saying he wasn&#8217;t going to. There were several talks that presented solutions to the callback craziness that is a natural side effect of async programming in JS today. [Jed Schmidt][9]&#8216;s [(fab)][10] talk was really entertaining and nicely done, though I fear that misplaced parens would lead to hard to debug problems. [Tim Caswell][11]&#8216;s [Step][12] library looks like a more straightforward solution to the problem.

By the way, apparently Python 2.5-style generators have a decent shot at appearing in a future ECMAScript spec. These can provide a nice solution for making async code look synchronous without bad side effects.

Brendan&#8217;s talk about [Proxy Objects][13] (an ECMAScript Harmony spec that is already implemented and widely used within Firefox) was enlightening. This is an absolutely fantastic new feature. As a long time Python programmer, I&#8217;ve missed a number of Python&#8217;s features for altering the behavior of objects (all of those &#8220;__&#8221; methods). Proxy Objects will bring this to JavaScript in a fashion that is way more powerful than the getters/setters support we have an ECMAScript 5 and it does so without forcing objects to have specially named methods. Very clean and nicely done.

Funny story: Saturday morning, Joe, Patrick and I were talking about the feasibility of making a fast, DOM-based code editing component, and whether that would help with accessibility. Later that day, [Fabian Jakobs][14] showed off [ACE][15], which is indeed a fast, DOM-based code editor. His presentation, which was overall nicely done, had a factual error about [Mozilla Skywriter][16]. He stated that Skywriter would be slow for a big canvas because it has to redraw every pixel for each character typed, which is rubbish. Skywriter does a saner job of painting than that&#8230; That said, his demo was very cool and their server has a lot in common with the server that we&#8217;re planning for Skywriter. Fabian and I agreed that it would be great to find ways for our projects to work together.

On Sunday, I spoke with Nick from [Shopify][17] who has also been working on code editing sorts of problems. He ended up with the <span style="text-decoration: line-through;">Canvas approach rather than DOM</span> DOM approach to editing also and his editor even uses Skywriter syntax highlighters. Nice!

As for Skywriter, I think our talk went reasonably well, albeit with a couple of technical glitches. My computer randomly decided to go to sleep early in the talk (huh?). After we got past that, we talked about how Skywriter is different from the original Bespin project and showed off the Bookmarklet and Embedded uses of Skywriter. We did a live coding portion of the talk in which we created a Skywriter plugin on the fly (a live version of a tutorial I wrote in June). We altered the script just before the talk to save a little typing by dropping the third parameter to window.open. It turns out that dropping the third parameter to window.open (at least in Firefox nightlies) results in a new window that doesn&#8217;t have a document body. Oops. Looks like a bug we need to report, or something. Pro Tip: don&#8217;t alter your live coding script by even a byte just before your talk!

I finally understand from [Kris Kowal][18]&#8216;s talk why Q.when is sometimes nicer than promise.then() (you can treat synchronous and asynchronous calls the same way), but I still think that promise.then is a fine way to go for many cases.

The conference venue was neat and very different from the typical US conference venue. Overall, the conference was simply great. The after parties were fun. My group also had a good chance to have some wide ranging discussions and work through some designs for Skywriter.

I&#8217;ll finish my wrap up of JSConf.eu with a note about the final talk: [Chris Williams][19]&#8216; Community.js talk. Chris and his wife Laura organized the two JSConf.us conferences, superbly I should add. Chris showed his more serious side, encouraging the JavaScript community to:

1. show respect for other languages as well, since most of us started with others
  
2. not to become JS fanbois
  
3. to fix the fact that Google searches for things like &#8220;javascript&#8221;, &#8220;learn javascript&#8221; and &#8220;javascript array&#8221; take you to pages that aren&#8217;t so great

For this last one, he&#8217;s set up a page at [promotejs.com][20] that encourages links to boost the [Mozilla Developer Network][21] (formerly Mozilla Developer Center) site. Apparently, there are still quite a few people who haven&#8217;t encountered MDC, which has a huge amount of very clearly written documentation for JavaScript, CSS and the browser environment. I do know many who google things like &#8220;mdc array&#8221; instead of &#8220;[javascript array][22]&#8220;, but ultimately, reclaiming those keywords is a worthy goal.

JavaScript is a powerful, general purpose, dynamic programming language with several very fast, compatible, cross-platform implementations and a runtime that is already in the hands of more than 1.5 billion people. JSConf is the best conference around for those who appreciate JS for what it is.

 [1]: http://directwebremoting.org/blog/joe/
 [2]: http://pcwalton.blogspot.com/
 [3]: http://blog.mozilla.com/axel/
 [4]: http://www.aminutewithbrendan.com/
 [5]: http://brendaneich.com/
 [6]: http://co-up.de/
 [7]: http://nodejs.org/
 [8]: http://higginsforpresident.net/
 [9]: http://jedschmidt.com/
 [10]: http://github.com/jed/fab
 [11]: http://howtonode.org/
 [12]: http://github.com/creationix/step
 [13]: http://wiki.ecmascript.org/doku.php?id=harmony:proxies&s=proxy%20object
 [14]: http://twitter.com/fjakobs
 [15]: http://github.com/ajaxorg/editor/
 [16]: http://mozillalabs.com/skywriter/
 [17]: http://www.shopify.com/
 [18]: http://askawizard.blogspot.com/
 [19]: http://voodootikigod.com/
 [20]: http://promotejs.com/
 [21]: https://developer.mozilla.org/en-US/
 [22]: https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Array