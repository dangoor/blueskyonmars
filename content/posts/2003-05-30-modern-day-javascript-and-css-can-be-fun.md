---
title: Modern Day JavaScript and CSS can be fun!
author: Kevin Dangoor
type: post
date: 2003-05-30T16:37:26+00:00
url: /2003/05/30/modern-day-javascript-and-css-can-be-fun/
categories:
  - Features
  - Software Development

---
The last time that I really spent any time directly working on web interfaces was in 1999, and I didn&#8217;t have a lot of time then to spend on a web UI. Lack of browser compatibility (and even support, in the case of CSS) made Javascript and CSS painful to use. Since 1999, my work has been focused on server-side technologies, because I have had other people to lean on to do the front end. Now, I&#8217;m in a 3 person group and the HTML is my concern&#8230; but, I&#8217;m actually enjoying it!
  
<!--more-->


  
I&#8217;ll start off by saying that I&#8217;m lucky. The tools that I&#8217;m developing are for an internal user community and I can guarantee that they will be running IE 6.0. Personally, I run Mozilla (more on that later). Knowing for certain the browser that my users will use, and the fact that said browser is at least somewhat modern makes my life a whole lot easier.

As I&#8217;ve been doing my work, I&#8217;ve wanted greater ease to make and revise pages, as well as the ability to provide a somewhat more &#8220;desktop-like&#8221; user experience. CSS and Javascript provide me with these things by separating content and layout, and by providing easy manipulation of what&#8217;s on the page via the DOM.

Unfortunately, as [Tim Bray was just saying][1], IE is _old_. (**Update**: Tim has added some [more commentary and links][2]). Sure, IE 6.0 is the most recent and probably the most standards-compliant IE there is, but it has really fallen behind Mozilla. Just try doing a position: fixed in a stylesheet or a document.styleSheets[0].cssRules[0] in Javascript to see what I mean. But, for my needs, I&#8217;ve been able to work out the differences without too much pain.

Why should I even bother using Mozilla myself if my user community uses IE? I greatly prefer using Mozilla for my own browsing, because there are no pop-unders, and type ahead find is great for navigating by keyboard. But it&#8217;s the great tools for web developers that puts it head and shoulders above IE for creating apps. The DOM Inspector and Javascript Debugger are hugely useful. Take a look, if you don&#8217;t believe me: Tools/Web Development.

Many people still have to deal with the fact that Netscape 4.76 and IE 5.0 are not completely dead. I don&#8217;t envy those people at all. But, as someone who is working exclusively with modern browsers, I&#8217;m enjoying myself. Sure, some things don&#8217;t work completely as expected&#8230; but they do enough of the time to make it worth stepping over the issues.

Useful Resources: [BrainJar][3] has some very nice use of CSS and nifty bits of Javascript that can teach a lot. There&#8217;s a fully-annotated pull-down menu system, and a windowing system.

I just came across (via [Scripting News][4]) the [CSS Zen Garden][5] which shows off what CSS is capable of.

[The DHTML Kitchen][6] has nice tutorials for putting together DHTML menus and tabbed interfaces.

And you may want to grab a handy [CSS Quick Reference Card][7] while you&#8217;re looking around.

 [1]: http://www.tbray.org/ongoing/When/200x/2003/05/28/CSS-IE
 [2]: http://www.tbray.org/ongoing/When/200x/2003/05/30/CSS26
 [3]: http://www.brainjar.com
 [4]: http://www.scripting.com
 [5]: http://www.csszengarden.com
 [6]: http://www.dhtmlkitchen.com
 [7]: http://www.digilife.be/quickreferences/quickrefs.htm