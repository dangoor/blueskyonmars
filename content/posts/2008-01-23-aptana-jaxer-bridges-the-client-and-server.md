---
title: Aptana Jaxer bridges the client and server
author: Kevin Dangoor
type: post
date: 2008-01-23T12:03:47+00:00
url: /2008/01/23/aptana-jaxer-bridges-the-client-and-server/
categories:
  - JavaScript
tags:
  - appjet
  - JavaScript
  - jaxer

---
I believe that we&#8217;re going to see some significant post-Rails server side web tools developments this year. TurboGears and Django were both never &#8220;Rails clones&#8221; because of their history and where they came from. But, all three promote a fairly similar idea of webapps are put together on the server.

Last month, [AppJet][1] provided a look at something different. It combined transparent persistence and, importantly, a seamless ability to run code on both the client and server.

A bigger deal, though, is [Aptana Jaxer][2] which has just been introduced. Jaxer runs the Mozilla engine _on the server_ and provides a mechanism for writing the server side of webapps in the same way that you write the client side (only without the browser compatibility headaches, of course!) You can manipulate the DOM using traditional JavaScript and have the server push out the changed document to the client. Jaxer will also automatically generate client->server proxy functions or copy code from the server to the client if you have code that needs to run in both places.

I think that Jaxer and AppJet are just the beginning. I&#8217;ll definitely be writing more about how the server is changing.

**Update**: I just noticed that Jaxer is licensed under the GPL. That complicates things a bit, because it seems more like a library than a compiler. In other words, you can&#8217;t freely give someone a copy of your app with Jaxer and not be forced to use the GPL. I&#8217;m not certain that you could even give them a copy of your app.

 [1]: http://appjet.com/
 [2]: http://aptana.com/jaxer