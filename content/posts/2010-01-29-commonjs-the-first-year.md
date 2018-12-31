---
title: 'CommonJS: the First Year'
author: Kevin Dangoor
type: post
date: 2010-01-29T14:53:34+00:00
url: /2010/01/29/commonjs-the-first-year/
categories:
  - JavaScript
tags:
  - CommonJS

---
A year ago today, I posted [&#8220;What Server Side JavaScript Needs&#8221;][1], inviting people to come and turn JavaScript into a competitive platform for applications on the server. Quite a few people answered the call. While the focus of the group has been on JavaScript in non-browser contexts, we&#8217;re ultimately shooting for as much of a standard that can cross between server, browser, GUI and command line applications as possible. That&#8217;s why we changed the name to [CommonJS][2] in the second half of the year. Ironically, most of my own personal use of CommonJS so far has been in the browser. I&#8217;ll come back to the personal perspective, though.

## The Original Goals

As laid out in my original blog post, we were seeking to create:

  * A module system,
  * A cross-interpreter standard library,
  * A few standard interfaces,
  * A package system, and
  * A package repository

Note that the idea here is that this group creates specs, which will have multiple implementations.

The goal is to have these things working across as many operating systems and interpreters as possible. There are three major operating systems (Windows, Mac, Linux) and four major interpreters (SpiderMonkey, Rhino, v8, JavaScriptCore). Plus there&#8217;s &#8220;the browser&#8221;, which is a unique environment unto itself. That&#8217;s a fair bit of surface area to cover.

Oddly, I think the one of those eight &#8220;platforms&#8221; with the poorest implementation support is Windows. Most of the CommonJS developers are using Macs or Linux machines, so I&#8217;m not sure how much time has really been spent on Windows. I would imagine that JavaScriptCore on Windows is probably the least supported combination.

The good news, however, is that there are projects using _all_ of those JavaScript interpreters and platform compatibility issues will ultimately be ironed out.

## CommonJS and the ECMAScript Standard

The CommonJS group is a grassroots effort, and not some formal standards body. In some ways, however, it works like a standards body in that the people working on the standard are also implementing the standard-in-progress and using it to build real applications.

We have no control over the ECMAScript language, which is managed by the TC39 working group. However, there are a few people involved in CommonJS who are part of TC39, and I have firsthand knowledge of others who are keeping an eye on how things are going with CommonJS.

The CommonJS standard-in-progress is designed to work on a subset of ECMAScript 5 that can be made to work on today&#8217;s ECMAScript 3 interpreters. ECMAScript 3 is the standard that is running in all of the browsers. In other words, in a CommonJS application you can count on Array.prototype.forEach to be implemented. Obviously, applications can do whatever they want (array destructuring? knock yourself out, but your app will only work on SpiderMonkey and Rhino).

One certainty about CommonJS is that inventing new language syntax is out of scope.

## The Module System

The CommonJS group has been remarkably good at avoiding bikeshedding. While there is discussion about names of things, there isn&#8217;t _heated_ discussion about it. People are far more interested in issues of functionality and ease-of-use. This is a very good thing, and it allowed us to get [modules][3] out of the way early on.

Of course, the lack of bikeshedding doesn&#8217;t mean that everyone agrees on things. The CommonJS module system has its controversial aspects, but I think it does well given the constraints:

  1. must work with ES3 syntax (destructuring could actually be useful, but we&#8217;re not going to do it)
  2. modules should have self-contained namespaces and be explicit about data the want to export
  3. it should be possible to make modules tamper-proof, though this is not a requirement
  4. using a module should be competitive with using modules in languages like Python and Ruby

TC39 had considered adding modules to ECMAScript 4 and there are module proposals on the table for ECMAScript Harmony that would add some syntax to JavaScript that would look similar to CommonJS modules. Here&#8217;s a short module to give you an idea of what CommonJS modules look like:

<pre>var sillymath = require("extramath/silly");

exports.addTwo = function(num) {
    return sillymath.add(num, 2);
};
</pre>

Personally, I find this to be reasonably concise with a nice level of explicitness. Some syntax sugar would be good, and I hope we get that in ES-Harmony. But, this syntax works fine today.

Of course, this syntax is not without controversy. The biggest controversy has been that require() is synchronous â€“ the &#8220;extramath/silly&#8221; module has to be available as the module above is loaded. However, there are a couple of reasonable ways to deal with this problem and I am happily working with CommonJS modules in the browser which is the environment that is least tolerant to synchronous loading.

Controversy or not, this basic module system was ratified last winter and has been implemented on all target environments of CommonJS.

Discussion is ongoing for a tie-in to the module standard: the [module transport][4] standard. Without additional help from the browser or some additional scaffolding running in the page, the module syntax above doesn&#8217;t work via a <script> tag. By standardizing what that scaffolding would look like, it is possible for a variety of build tools, servers and client side libraries to come into existence to provide many options for loading modules in the browser. There have already been several implementations of CommonJS module loading in the browser, but a standard will make it much easier to mix-and-match client and server.

## The Standard Library

I had hoped we&#8217;d get farther on the standard library than we have, but it can indeed be a long process. [system][5] and [unit testing][6] are the only ones that have been ratified at this point. We have come a long way on file access.

&#8220;What!?!?&#8221;, I hear you say, &#8220;there&#8217;s no standard for accessing files yet?&#8221; That&#8217;s right. And there are a couple of reasons that it&#8217;s been challenging to get there.

Consider that JavaScript does not even have a standard object to deal with _binary data_. That is a basic prerequisite to working with files. JavaScript strings are not the same as a binary data container. So, there&#8217;s binary data to handle, streams to figure out and then file functionality built on top of that. There&#8217;s also the consideration of whether file access is synchronous or asynchronous. We&#8217;ve made tons of headway on this, and there are certainly implementations of some of the specs. It&#8217;s just a matter of finishing them.

I&#8217;m hoping to see [promises][7] become a part of the standard, because some form of that interface is very convenient to use for asynchronous operations.

## Standard Interfaces

We do have a very useful interface with implementations and people actively using it: the [JavaScript Gateway Interface (JSGI)][8]. That spec has not yet been ratified, but it is getting closer and there are apps being built against it today.

Database access has not yet been standardized. It will be interesting to see if we can come up with a good interface that can usefully target SQL and NoSQL databases alike.

## Package System

We have a recently ratified spec for [packages of CommonJS code][9]. I hope this will bring about a collection of good package managers with different focuses and targeting different environments. There have already been a couple of attempts to create package management systems, and the most fleshed out one that I&#8217;ve seen is Tusk, which is bundled with [Narwhal][10]. Once a few more specs are ratified, Tusk should be able to run on other CommonJS implementations.

## Package Repository

Tusk is using [GitHub][11] as a package repository, and that is working okay for the time being. A couple weeks back, we got word that the [jQuery plugin repository is going to provide a CommonJS package.json file][12] for the ~5000 plugins in their database. This is exciting, because this infrastructure could prove to be very useful to us going forward.

## JavaScript: Bubbling Up

2009 was a terrific year for JavaScript. In the browser, we&#8217;ve obviously seen tons of growth in increasingly sophisticated applications. I think the interest is steadily building to use JavaScript more and more outside of the browser. The two JSConf conferences (in [Washington DC][13] and [Berlin][14]) were great successes by all accounts I&#8217;ve seen. [PhoneGap][15], [Titanium][16] and Palm&#8217;s [WebOS][17] have created ways for people to use web tech to create installable apps for mobile phones. [node.js][18] has been a huge driver for people to check out building scalable, asynchronous JavaScript apps on the server. And, of course, CommonJS is finding its way into more and more applications.

## My Personal View

I had hoped to personally have more time to devote to CommonJS in 2009, but I am delighted at how a great collection of people have stepped in and carried the specifications and implementations forward through a lot of hard work and force of will. More than 5,100 messages have gone across the mailing list, and more than 10% of those have been from [Kris Kowal][19]. Kris has done a ton of work in ironing out many of the specs and deserves a good deal of credit for where CommonJS is today. He and [Tom Robinson][20] even stood in for me when I had to cancel my trip to JSConf.eu (thanks, guys!).

Taking a look at the [top posters on the googlegroup][21], you can see how many people have put so much into CommonJS. More than 10 people have contributed more than 100 messages a piece and, for many of those people, there was a lot of time spent in the email discussions, IRC chats, spec writing and implementation of those specs. Plus, as early adopters, they have the joy of tweaking things as the specs have changed over time. Thanks to all of you for the dedication and the will to get it done.

[Bespin][22]&#8216;s client side JavaScript code is all CommonJS modules now, partly thanks to the efforts of [Charles Jolley][23] to migrate the [SproutCore][24] framework to CommonJS and creating the Tiki module loader. From that standpoint, I&#8217;m already using more CommonJS now than I did in 2009. I&#8217;m also hoping that 2010 will bring a Bespin server &#8220;reboot&#8221;, where we start migrating server functionality to CommonJS.

On the whole, I think that 2009 was a great year for JavaScript and CommonJS and I think 2010 is going to be even bigger. I hope to meet more enthusiastic JavaScript hackers at JSConf.us in April!

### Comments?

You can direct them to the [thread on the CommonJS googlegroup][25] or email to <editor@blueskyonmars.com>.

 [1]: http://www.blueskyonmars.com/2009/01/29/what-server-side-javascript-needs/
 [2]: http://commonjs.org/
 [3]: http://wiki.commonjs.org/wiki/Modules/1.1
 [4]: http://wiki.commonjs.org/wiki/Modules/Transport
 [5]: http://wiki.commonjs.org/wiki/System/1.0
 [6]: http://wiki.commonjs.org/wiki/Unit_Testing/1.0
 [7]: http://wiki.commonjs.org/wiki/Promises
 [8]: http://wiki.commonjs.org/wiki/JSGI/Level0/A/Draft2
 [9]: http://wiki.commonjs.org/wiki/Packages/1.0
 [10]: http://narwhaljs.org/
 [11]: http://github.com/
 [12]: http://groups.google.com/group/commonjs/browse_thread/thread/39dcdede35edcddd
 [13]: http://jsconf.us/
 [14]: http://jsconf.eu/
 [15]: http://phonegap.com/
 [16]: http://www.appcelerator.com/
 [17]: http://developer.palm.com/
 [18]: http://nodejs.org/
 [19]: http://askawizard.blogspot.com/
 [20]: http://tlrobinson.net/
 [21]: http://groups.google.com/group/commonjs/about
 [22]: http://mozillalabs.com/bespin/
 [23]: http://www.okito.net/
 [24]: http://sproutcore.com/
 [25]: http://groups.google.com/group/commonjs/browse_thread/thread/53c59828899ffcd9