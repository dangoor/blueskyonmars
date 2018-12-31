---
title: Bespin and jQuery
author: Kevin Dangoor
type: post
date: 2010-05-25T16:21:37+00:00
url: /2010/05/25/bespin-and-jquery/
categories:
  - Bespin
  - JavaScript

---
<div id="magicdomid669">
  Yesterday, we announced that the Bespin server is going to be <a href="http://groups.google.com/group/bespin/browse_thread/thread/6de8c718d64232a0">rebuilt from the ground up in node.js</a> with a decentralized model in mind. I&#8217;ve seen a lot of positive reaction to that, which is great because I think it&#8217;s an important step forward for Bespin. We also mentioned on bespin-core that <a href="http://groups.google.com/group/bespin-core/browse_thread/thread/66c1e46896688868">we have changed from SproutCore</a>, which we adopted during the &#8220;reboot&#8221; of the Bespin client side code, to jQuery. A handful of people have suggested that we should just build our own &#8220;framework&#8221;. Our decision to use jQuery came after much deliberation, so I thought I&#8217;d go into a little detail about that since this question has now come up many times.
</div>

## What is Bespin? {#magicdomid714}

<div id="magicdomid913">
  It&#8217;s hard to say if something is a good choice for Bespin without actually being clear about what Bespin is. <strong>Bespin is a customizable programming environment for web applications</strong>. There are at least two correct ways to interpret that sentence:
</div>

  1. Bespin is a programming environment that you can include in your web applications that you create
  2. Bespin is a programming environment for creating web applications

<div id="magicdomid1330">
  Early in Bespin&#8217;s life, people were embedding the editor in their own applications, but this wasn&#8217;t well supported. We made a decision to make that a well-supported use of our project and that change has major ramifications for the project.
</div>

## Frameworks vs. Libraries {#magicdomid698}

<div id="magicdomid1458">
  The best description of the <a href="http://www.artima.com/forums/flat.jsp?forum=106&thread=152104">difference between a framework and a library</a> that I&#8217;ve seen is:
</div>

<div id="magicdomid1464">
  <ul>
    <li>
      A libraryÂ  is something you call from your code
    </li>
  </ul>
</div>

<div id="magicdomid1474">
  <ul>
    <li>
      A framework is something that calls your code
    </li>
  </ul>
</div>

<div id="magicdomid2051">
  Note that this definition says nothing about the size (libraries could certainly be bigger than frameworks, and vice versa). This definition also makes no judgments about which is better or whether the code is loosely coupled or tightly coupled.
</div>

<div id="magicdomid1911">
  Frameworks can make building an application <em>really</em> fast. They do a great job of reducing the amount of code you need to write, as long as your application fits the framework&#8217;s design and intended applications well. The farther you stray from the path, the more resistance you&#8217;ll get as you try to add new things.
</div>

<div id="magicdomid2330">
  SproutCore is a framework. It attaches event handlers to the page and delegates those events to views that you create. Further, it has a powerful declarative binding/observation system that it updates automatically as part of a runloop that it maintains. It&#8217;s really quite a powerful GUI toolkit that runs entirely in your browser.
</div>

<div id="magicdomid5997">
  For Bespin &#8220;the application&#8221; (the software that runs at bespin.mozillalabs.com), SproutCore seemed like it would be a good fit because what we were doing was more like a desktop app than a website. On the other hand, for Bespin &#8220;the customizable, embeddable editor&#8221;, the tools we want and need are not such a great fit for a framework. Bespin needs to fit in well with what people are already doing on their pages.
</div>

## Why use a library at all? {#magicdomid2674}

<div id="magicdomid5975">
  OK, so Bespin and frameworks are not a good match. But there are plenty of libraries out there (jQuery, YUI, Prototype, Mootools, Dojo, Closure, and even MochiKit about which I&#8217;ve written extensively in the past) Why not just build our own set of utilities, especially since Bespin exclusively targets modern browsers?
</div>

<div id="magicdomid6002">
  We wrestled a bit with that very question. Even with modern browsers, some conveniences are still handy. Here&#8217;s a simple case I can point to: addClass. A function that will add a CSS class to a DOM node. We all need to do that at times, but it&#8217;s not yet a method offered by the DOM, nor is it in any proposed standard that I&#8217;ve seen.
</div>

<div id="magicdomid3630">
  I believe that every JavaScript library offers addClass. Their APIs vary, but it&#8217;s in there somewhere. We could create our own library with our own version of addClass. But that has disadvantages:
</div>

<div id="magicdomid6003">
  <ul>
    <li>
      we have to write it/test it ourselves or copy it from somewhere
    </li>
  </ul>
</div>

<div id="magicdomid6023">
  <ul>
    <li>
      we have to maintain it
    </li>
  </ul>
</div>

<div id="magicdomid3837">
  <ul>
    <li>
      for people extending Bespin, there&#8217;s that much more surface area that they need to learn
    </li>
  </ul>
</div>

<div id="magicdomid4086">
  <ul>
    <li>
      we need to write docs for it
    </li>
  </ul>
</div>

<div id="magicdomid4571">
  <ul>
    <li>
      we can&#8217;t use fancier things people create (overlays, trees, etc.) without porting them
    </li>
  </ul>
</div>

<div id="magicdomid4688">
  <ul>
    <li>
      if people already have a library on their page, our utilities will add additional size
    </li>
  </ul>
</div>

<div id="magicdomid4051">
  There are probably other disadvantages as well. The only advantages I see to rolling our own are:
</div>

<div id="magicdomid4003">
  <ul>
    <li>
      we get exactly the functionality we need and no more
    </li>
  </ul>
</div>

<div id="magicdomid4044">
  <ul>
    <li>
      we maintain our own release schedule for it
    </li>
  </ul>
</div>

<div id="magicdomid4668">
  We are considering a &#8220;best of both worlds&#8221; approach as well, if we feel like slimming down Bespin Embedded &#8220;Drop In&#8221; (the prepackaged single .js file) even further: we take just the functionality we&#8217;re interested in from a library (jQuery) and create our own mini library that uses the exact same API. Our modules/build tooling can make it transparent to switch between the mini library, the full library and one that is already on the page.
</div>

## Why jQuery? {#magicdomid4705}

<div id="magicdomid5091">
  As I mentioned earlier, when it comes to utilities the libraries all offer a very similar collection of functions. We don&#8217;t want to use a library that &#8220;leaks&#8221; onto the page, either through the creation of globals or the extension of built-in prototypes. That still leaves a number of choices. We evaluated some, but ultimately decided on jQuery because:
</div>

<div id="magicdomid5122">
  <ul>
    <li>
      It&#8217;s <a href="http://www.webdirections.org/sotw10/">very popular</a>, which increases the chance that it&#8217;s already on the page (and decreases the size of Bespin)
    </li>
  </ul>
</div>

<div id="magicdomid5252">
  <ul>
    <li>
      many people are already familiar with it
    </li>
  </ul>
</div>

<div id="magicdomid5224">
  <ul>
    <li>
      there&#8217;s lots of good documentation available
    </li>
  </ul>
</div>

<div id="magicdomid6041">
  <ul>
    <li>
      there are many decent open source plugins that people can use when extending Bespin
    </li>
  </ul>
</div>

<div id="magicdomid6091">
  It&#8217;s worth noting that these are not technical reasons to use jQuery, and these largely only matter because jQuery is popular and Bespin is intended to be used on other peoples&#8217; pages. The choice of jQuery for Bespin is not a technical choice. We certainly like jQuery, but we like the other libraries as well.
</div>

## Not just jQuery {#magicdomid5423}

<div id="magicdomid5817">
  One more important point: Bespin Embedded is still designed to be easily built into a self-contained .js file. The current code in our repository puts only one name on the page (bespin) and everything else is hidden away conveniently inside of there. The next release of Bespin Embedded will be <em>less than half</em> the size of the previous release, even with jQuery bundled in. So, Bespin will be a good addition to your application, regardless of which JavaScript library you might use for the rest of your code.
</div>

## Summary {#magicdomid6103}

<div id="magicdomid6454">
  Bespin has had unusual and competing requirements along the way and as we&#8217;ve zeroed in on exactly what Bespin is and will become, we&#8217;ve changed our infrastructure to match the needs of the project. We&#8217;re really excited about how far we&#8217;ve come since &#8220;rebooting&#8221; the project and are looking forward to these next few releases that lead up to a &#8220;1.0&#8221; of the Bespin project.
</div>

## Additional Commentary

John-David Dalton [commented via a gist][1].
  


He points out that unless we are using a compatible jQuery, people who already have jQuery on the page will not have any size advantage. Of course, if we have our own library _no one_ will gain a size advantage.

With respect to Bespin users being able to use whatever library they wish without porting additional widgets, we (the Bespin team) want to be able to use things like trees and such without having to port them to our own library. Bespin users do remain free to use whatever they wish without porting anything.

Finally, regarding &#8220;fourth time&#8217;s a charm&#8221;, I&#8217;ll just note that the 0.8 version number of the next release of Bespin is actually significant. The client APIs are settling.

Thanks for the comment, jdalton!

## ClassList API in HTML5

I was happy to hear from Thomas Bassetto that addClass has indeed been rendered redundant by [HTML5&#8217;s ClassList API][2] which looks great. element.classList is available today in Firefox 3.6 and, according to the Mozilla Hacks article, WebKit is planning to also support the API. The current version of Chrome does not have it yet.

 [1]: http://gist.github.com/413709
 [2]: http://hacks.mozilla.org/2010/01/classlist-in-firefox-3-6/