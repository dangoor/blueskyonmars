---
title: How much code in the browser is too much?
author: Kevin Dangoor
type: post
date: 2005-07-07T12:26:11+00:00
url: /2005/07/07/how-much-code-in-the-browser-is-too-much/
keywords:
  - javascript,programming
categories:
  - Software Development

---
With the ascent of AJAX, many people are writing or considering writing more code to run in browser than they had in years. JavaScript, once left for dead as being too incompatible and impossible to debug, is now being viewed as something usable.

Firefox/Mozilla has certainly helped the renaissance. With an honest-to-goodness [debugger][1], plus a super-handy [web developer toolbar][2], you can really get a view into once going on. [Selenium][3] provides a mechanism to run tests in-browser, so that you can get all of the benefits of an automated test suite making sure your code works in different browsers.

All of this recent goodness is causing people to start approaching JavaScript as a real programming language. However, JavaScript is still implemented a bit differently between browsers, and its object model is definitely different from what most people are used to. Ian Bicking [wrote about his troubles working with Prototype.js&#8217;s extended object model][4]. Bob Ippolito [has been writing all month][5] about JavaScript warts when it comes to real programming.

If you take a look at the [kinds of things][6] that Bob is implementing, you&#8217;ll get the idea that Bob is trying to do real development in-browser, turning it into a real layer in an application. Given that people have made sophisticated email programs and spreadsheets in JavaScript, people have certainly done this before. But, most of the scripts I&#8217;ve seen have been focused on [whizzy special effects][7].

So, to the question then: how much _should_ you do with JavaScript? For just about any application, I would say that the answer is &#8220;as much as you can&#8221;. Assuming you don&#8217;t have some weird requirement to support Netscape 4.x or IE on the Mac, and I feel sorry for you if you do, you can reasonably do quite a bit in JavaScript. The limiting factor will likely be JavaScript performance.

JavaScript is slow. Don&#8217;t believe me? Check out something computationally intensive like [encryption][8] or trying doing an [XSL transform][9] without native browser support (you&#8217;ll have to use Safari for that, to see what I mean).

The benefit to using JavaScript can be huge, though. Even though it is slower than the language being used on the server side, that work is being done off of your server. If you&#8217;re careful about how much data you feed to the browser to process, quite a bit of the formatting work can be offloaded there. And, if you [take advantage of native code][10] as much as possible, you can even handle fairly sizable chunks of data.

Given the value in doing JavaScript today, a framework like Bob Ippolito&#8217;s MochiKit that extends JavaScript&#8217;s object model can seriously ease the burden of putting together robust code that runs in-browser. JavaScript is definitely entering a new era.

 [1]: http://www.hacksrus.com/~ginda/venkman/
 [2]: https://addons.mozilla.org/extensions/moreinfo.php?id=60
 [3]: http://selenium.thoughtworks.com
 [4]: http://blog.ianbicking.org/prototype-and-object-prototype.html
 [5]: http://bob.pythonmac.org/archives/2005/07/
 [6]: http://bob.pythonmac.org/archives/2005/07/01/javascript-frameworks/
 [7]: http://script.aculo.us/
 [8]: http://www.fourmilab.ch/javascrypt/
 [9]: http://goog-ajaxslt.sourceforge.net/
 [10]: http://johnvey.com/features/deliciousdirector/