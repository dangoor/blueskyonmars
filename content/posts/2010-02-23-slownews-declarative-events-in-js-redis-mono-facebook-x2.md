---
title: 'SlowNews: Declarative Events in JS, Redis, Mono, Facebook x2'
author: Kevin Dangoor
type: post
date: 2010-02-23T14:00:37+00:00
url: /2010/02/23/slownews-declarative-events-in-js-redis-mono-facebook-x2/
categories:
  - SlowNews

---
## Ending _This_ SlowNews Experiment

This is the last issue of this SlowNews format. I may or may not try a new format. I&#8217;ve written [a bit more about why][1].

## Reactive JavaScript: Declarative Programming for Events

When a problem space is well understood, adding declarative forms can really save on a lot of work. Here&#8217;s an [interesting look at the Reactive Extensions to JavaScript][2], created by the team at Microsoft that creative the [Reactive Extensions for .NET][3]. I didn&#8217;t find the syntax there appealing, but the ideas are interesting. The [Flapjax][4] project provides a nicer looking syntax, but requires a compilation step to pure JS (the compiler is written in JS and can run in the browser). I like the Flapjax tutorial reference to spreadsheets, because spreadsheets provide a great model for certain kinds of declarative work and tying declarative structures with additional imperative programming is very powerful. One of the reasons we chose [SproutCore][5] for Bespin is the ability to bind views directly to data so that the two automatically stay in sync.

## A Collection of Redis Use Cases

Mathias Meyer&#8217;s [Collection of Redis Use Cases][6] provides a great collection of examples to give you an idea of where you might apply [Redis][7] in your own applications. In the &#8220;Not Only SQL&#8221; movement, Redis is a good tool to have in your toolbox.

## Using node.js To Bootstrap a Server from Client Code

Dion Almaer wrote up the experience he and Ben Galbraith had [in creating][8] the [Project Appetite][9] site for Palm WebOS developers. Following the modern style of having the client do presentation and the web server just providing an API, they could work on client and server independently. It turns out that a quick way to get a server up and running was just to reuse client-side code on the server (in this case, using [node.js][10]).

## Harmony: JavaScript Testing in Ruby

[Harmony][11] takes advantage of [Johnson][12], a Ruby to JavaScript bridge and lets you write unit tests for your JavaScript code in Ruby. It&#8217;s not unreasonable to ask _why_, given that you can write the tests for your JavaScript code in, say, JavaScript&#8230; but, on first glance to me, the benefit here would seem to be that you can test server and client bits together conveniently.

## Making Facebook 2x Faster

Jason Sobel gives the rundown on a 2009 project to [make Facebook&#8217;s pages load twice as fast][13]. This is a good account of what it can take to make a speedy site.

## Thoughtworkers Subjective Impressions of VCS

Having trouble picking a version control system (VCS) for your next project? Martin Fowler has posted [some general impressions][14] that Thoughtworks people have picked up while working on client projects. I&#8217;ve worked on a variety of projects using a variety of tools (RCS, CVS, ClearCase, Subversion, Bazaar-NG, Mercurial, Git) and Martin&#8217;s roundup meshes pretty well with my own impressions.

## Canviz: graphviz on Canvas

Need to produce a directed graph? Only care about the [&#8220;modern&#8221; browsers][15]? Then [canviz][16] is for you! [Canviz is open source][17] (MIT license) and lets you create a variety of graphs just as you can with the [graphviz][18] project, but entirely client side.

## HTML5 Web Sockets Spec Reimagined

Tim Bray [dove into the HTML5 spec][19] and found a number of new features that he liked. He also went deep on the Web Sockets spec in particular, going so far as to produce an [alternate version of the spec][20] to make things clearer. Looking at Tim&#8217;s alternate, there&#8217;s a lot that he left alone.

## State of Mono

Miguel de Icaza has written up an overview of [what&#8217;s been going on with the Mono project][21]. It looks to me like the Mono platform is still evolving quite nicely. If you happen to be near Ann Arbor on Thursday, February 25th, you can learn about the state of .NET web development at the [a2][22] 

<div>
  meeting.</p> 
  
  <h2>
    10 Online Code Editors
  </h2>
  
  <p>
    There has been a lot of development in web-based code editors, and I think this space will just get busier as time goes on. Here&#8217;s a roundup of <a href="http://www.catswhocode.com/blog/10-useful-online-code-editors">10 online code editors</a>, including screenshots. ObDisclaimer: I&#8217;m the project lead for <a href="https://mozillalabs.com/bespin/">Bespin</a>.
  </p>
  
  <h2>
    Interesting Releases
  </h2>
  
  <ul>
    <li>
      <a href="http://www.kernel.org/pub/software/scm/git/docs/RelNotes-1.7.0.txt">git 1.7</a>
    </li>
    <li>
      <a href="http://razorjack.net/quicksand/">jQuery Quicksand plugin</a> &#8211; nice visual effect for filtering and sorting
    </li>
    <li>
      <a href="http://code.google.com/p/zen-coding/wiki/Changelog">Zen Coding 0.6</a> &#8211; adds filters, new editor support and a bunch of other features
    </li>
  </ul>
  
  <h2>
    > list<br /> 11 goto 11
  </h2>
  
  <p>
    Top 11 ways to deploy a website
  </p>
  
  <p>
    11. <a href="http://samba.anu.edu.au/rsync/">rsync</a><br /> 10. <a href="http://labs.peritor.com/webistrano">Webistrano</a><br /> 1. <a href="http://renesd.blogspot.com/2010/02/secret-to-my-web-development.html">Your foot!</a>
  </p>
</div>

<div class="zemanta-pixie">
  <img class="zemanta-pixie-img" src="http://img.zemanta.com/pixy.gif?x-id=c026fe09-9c9f-877e-b199-90661aba1f68" alt="" />
</div>

 [1]: http://www.blueskyonmars.com/2010/02/23/ending-slownews-experiment-1/
 [2]: http://codebetter.com/blogs/matthew.podwysocki/archive/2010/02/16/introduction-to-the-reactive-extensions-to-javascript.aspx
 [3]: http://msdn.microsoft.com/en-us/devlabs/ee794896.aspx
 [4]: http://www.flapjax-lang.org/
 [5]: http://sproutcore.com/
 [6]: http://www.paperplanes.de/2010/2/16/a_collection_of_redis_use_cases.html
 [7]: http://code.google.com/p/redis/
 [8]: http://almaer.com/blog/building-an-web-application-from-the-inside-out-using-node-js-to-bootstrap-a-server-from-client-js?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+dion+%28techno.blog%28%22Dion%22%29%29
 [9]: http://projectappetite.com/
 [10]: http://nodejs.org/
 [11]: http://github.com/mynyml/harmony
 [12]: http://github.com/jbarnette/johnson/
 [13]: http://www.facebook.com/note.php?note_id=307069903919
 [14]: http://martinfowler.com/bliki/VersionControlTools.html
 [15]: http://code.google.com/p/canviz/wiki/Browsers
 [16]: http://www.ryandesign.com/canviz/
 [17]: http://code.google.com/p/canviz/
 [18]: http://www.graphviz.org/
 [19]: http://www.tbray.org/ongoing/When/201x/2010/02/15/HTML5
 [20]: http://www.tbray.org/drafts/wsock-00
 [21]: http://tirania.org/blog/archive/2010/Feb-17.html
 [22]: http://a2div.com/