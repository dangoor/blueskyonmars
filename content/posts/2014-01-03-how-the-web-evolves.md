---
title: How the Web Evolves
author: Kevin Dangoor
type: post
date: 2014-01-03T13:56:36+00:00
url: /2014/01/03/how-the-web-evolves/
categories:
  - JavaScript

---
Two years ago, I made a mistake in posting <a href="https://plus.google.com/app/basic/stream/z124vxybvqf2ixcg504ccxgwwuebyh4rb1s" target="_self" title="">this overly succinct statemen</a>t to Google+:

> Web SQL Database needs to die. The sooner IndexedDB is in the hands of developers the better.

Tweet-sized statements often don&#8217;t capture enough of the nuances of a thought to communicate well.

My big mistake was in not being clear enough about _why_ Web SQL Database needed to die. I tried to explain why the proposed standard was problematic for some browser vendors and such, but fundamentally my opinion is really that we needed to have _some_ **standard way to store reasonable amounts of data for offline and online uses and to be able to access that data efficently**. Web SQL DB would meet that criteria if it weren&#8217;t _dead_. I&#8217;m sympathetic to the issues that some browsers have with Web SQL DB (I did work for Mozilla, after all!), but at the end of it I just really want the web platform to have all of the capabilities it needs. Data storage is a pretty basic thing.

Of course, reality is more complicated than &#8220;Web SQL DB is dead&#8221;. All of those hundreds of millions of iOS devices today only <a href="http://caniuse.com/#search=Database" target="_self" title="">support Web SQL and not IndexedDB.</a> Many people on the Google+ thread have a strong preference for SQL vs. the API that IndexedDB has to offer. But, the fact remains that the <a href="http://www.w3.org/TR/webdatabase/" target="_self" title="">Web SQL Database proposed standard</a> has had a giant disclaimer at the top since 2010 stating that it has reached an impasse.

But, this blog post is not about WebSQL DB vs. IndexedDB. Web platform features like these don&#8217;t just _poof_ into existence. With today&#8217;s process, these features are designed, tested in browsers, formalized, argued about and standardized by various groups of people. The web is not like some proprietary platform where a vendor suddenly drops a new version with a bunch of new features on everyone. By knowing how the standards come to exist, _you_ can help ensure that the platform does what it needs to do for your apps.

Alex Russell spoke with the people of JavaScript Jabber <a href="http://javascriptjabber.com/087-jsj-tc39-with-alex-russell/" target="_self" title="">about TC-39 (the group that standardizes JavaScript)</a>, but Alex also has a lot to say about the evolution of the rest of the web platform as well. If you&#8217;ve ever had trouble with HTML5 application cache while trying to make an offline web app, Alex has been working on a new API, <a href="https://github.com/slightlyoff/ServiceWorker/" target="_self" title="">Service Worker,</a> that will make your life better. He&#8217;s also been quite involved in the <a href="http://www.w3.org/TR/components-intro/" target="_self" title="">Web Components</a> work. And, of course, as one of the founders of the <a href="http://dojotoolkit.org" target="_self" title="">Dojo Toolkit</a>, he&#8217;s been at this for a bit longer than just about anyone.

Yehuda Katz gave a talk a few months ago (<a href="http://www.youtube.com/watch?v=EcyxXPILO8E" target="_self" title="">&#8220;The Future of the Client Side Web&#8221;</a>) in which he spoke about how the standards are made and where they&#8217;re going. Yehuda also has tons of experience with both server side and client side development and he&#8217;s part of both <a href="http://emberjs.com" target="_self" title="">Ember</a> and jQuery core teams.

Alex and Yehuda are real-world web developers who have taken the step of helping to build out the standards themselves. They are both part of the W3C&#8217;s <a href="http://www.w3.org/2001/tag/" target="_self" title="">Technical Architecture Group (TAG)</a>. Speaking of which, TAG elections are coming up and the super-sharp David Herman (who has done a ton of amazing work on <a href="http://wiki.ecmascript.org/doku.php?id=harmony:modules" target="_self" title="">modules for the next version of JavaScript</a>) and Domenic Denicola (who has helped tremendously in pushing <a href="https://github.com/domenic/promises-unwrapping" target="_self" title="">Promises for JavaScript</a>) are <a href="http://calculist.org/blog/2014/01/02/i-m-running-for-the-w3c-tag/" target="_self" title="">running for the TAG</a>.

The web platform is built by real people who want the platform to be the best it can be. Understanding this is the best way to ensure that the web gets the features that you need for your applications.