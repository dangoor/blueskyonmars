---
title: Initial thoughts on Eclipse’s Orion
author: Kevin Dangoor
type: post
date: 2011-03-22T16:01:57+00:00
url: /2011/03/22/initial-thoughts-on-eclipses-orion/
categories:
  - Mozilla
  - Software Development

---
Last week, I had the opportunity to join a planning meeting for the newly coming together [Orion][1] project. Orion is a new take on the IDE coming from some people with a raftload of IDE experience with Eclipse. Orion is also a new take on the web-based IDE, which is something Iâ€™ve enjoyed exploring a bit through the Bespin project.

The meeting brought together people from the Eclipse Foundation, IBM, SAP, Microsoft, Nokia, RIM, GitHub, Nitobi and I represented Mozilla there. [Rik Arends][2] from [Ajax.org][3], makers of [Cloud9 IDE][4], also made it to the meeting, which was really cool. I like the way that open source â€œcompetitorsâ€ are often willing to exchange knowledge and ideas in ways in which traditional commercial competitors are not.

Cloud9 and Orion are taking two different approaches to the IDE-in-the-cloud concept. Cloud9 is similar to Bespin and can be thought of as something like the â€œGoogle Docs of Codeâ€. Itâ€™s a â€œsingle page appâ€ that provides something akin to the desktop editor experience in your browser. Orion is taking the approach of being â€œcompletely webbyâ€. Instead of a single page app, each URL represents a tool+resource, much more like a â€œCGI-styleâ€ webapp. Practically, this means that when youâ€™re navigating your files, youâ€™re using a page whose sole purpose is file navigation. When youâ€™re editing, youâ€™re using an editor page that has a URL that refers to the file youâ€™re editing. When youâ€™re committing to a git repository, you go to a git page.

The offshoot of Orionâ€™s approach is that Orion does not provide UI bits like a tabbed editing interface. Instead, if you want to open multiple files you just open multiple browser tabs. Not only does this mean that the Orion folks have less code to maintain, it also lets them automatically take advantage of neat browser features like [Firefox 4â€™s Panorama][5].

One of the keys to the Orion approach is that rather than trying to invent everything and house it within Orion, they want to effectively make the whole web part of Orion (or, put another way, they want Orion to just be part of the web). Rather than giving Orion a â€œnew project wizardâ€, they can just link over to [Initializr][6], for example.

This is a powerful idea. The webâ€™s loose coupling is likely one of the reasons it has been so wildly successful, and thatâ€™s what Orion wants to tap into. The tension is going to come when they try to provide an nicely integrated and consistent user experience for common tasks. If you look at Cloud9 and Orion today, youâ€™ll see what I mean. Cloud9 already has a polished and consistent flow that Orion presently lacks.

Part of Orionâ€™s solution to this problem is through the use of plugins. Orionâ€™s plugin system is far simpler than that of Eclipse and is also quite webby. Plugins are basically HTML pages that are loaded through iframes. This means that plugins have automatic security restrictions imposed by the browser. They communicate with the rest of Orion through postMessage. That means that only JSON data passes between plugins and Orion (no code can get through) and only the APIs that Orion provides at the other side of the postMessage bridge are accessible.

That plugin system is loosely coupled and can be used on its own. If youâ€™ve got a JavaScript app that you want to make extendable, you should check it out.

John Barton (IBM and Firebug) demoed Firebug with editing integration with Orion. The Orion server provided the browser with a header with the URL to edit the file being served. Firebug used this header to provide an â€œedit with Orionâ€ feature. John showed off editing integration for CSS where the changes to the CSS made in Orion were instantly reflected in the browser. Nicely done! One of the most popular requests to the Firebug project is the desired ability to be able to save changes made to the CSS via Firebugâ€™s UI. There are some solutions available as [Firebug extensions][7], but Orion potentially provides another solution that will integrate very nicely.

There were quite a few times in our discussions where topics and issues that came up were exactly things that we had dealt with for Bespin. [Ben][8] and [Dion][9] came by and presented about their experiences with Bespin. We all want to see this kind of exploration make progress and are happy to help people avoid the mistakes we made and the pitfalls we encountered.

The activity around Cloud9 IDE and Orion is great to see, because browser-based development is one area that is not yet the norm for web developers but I think will come to be at some point in the future.

 [1]: http://wiki.eclipse.org/Orion
 [2]: http://twitter.com/#!/rikarends
 [3]: http://ajax.org/
 [4]: http://c9.io/
 [5]: http://support.mozilla.com/en-US/kb/what-are-tab-groups?redirectlocale=en-US&redirectslug=what-panorama
 [6]: http://initializr.com/
 [7]: http://getfirebug.com/wiki/index.php/Firebug_Extensions
 [8]: http://benzilla.galbraiths.org/
 [9]: http://almaer.com/blog/