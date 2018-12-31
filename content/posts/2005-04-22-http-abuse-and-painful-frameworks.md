---
title: HTTP abuse and painful frameworks
author: Kevin Dangoor
type: post
date: 2005-04-23T06:02:48+00:00
url: /2005/04/22/http-abuse-and-painful-frameworks/
categories:
  - Software Business

---
Ryan Tomayko had commented on [my post from yesterday][1] regarding using HTTP correctly (not abusing HTTP GET, etc.). My posting was following the pragmatic perspective of getting things done without worrying about absolute correctness. I agree with Ryan&#8217;s new posting [&#8220;On HTTP Abuse&#8221;][2]. Favoring &#8220;getting things done&#8221; doesn&#8217;t also mean that I _don&#8217;t_ want to do things correctly. His post is correct that the frameworks that we use to get real work done just don&#8217;t lend themselves to using HTTP fully and correctly.

My guess is that many of the frameworks were created in the process of trying to get some job done. Especially given the nature of what&#8217;s easily testable with the browsers we have today, I can imagine how the frameworks we use came to be the way they are. It&#8217;s a non-trivial task to make a framework that encourages proper use of HTTP and exposes its full power while still being as easy as what we have today.

But, we do today have browsers that do a reasonable job of HTML/CSS/DOM, so it&#8217;s not inconceivable that we could have server side frameworks and browsers that let us really exploit all that HTTP can offer.

 [1]: http://www.blueskyonmars.com/archives/2005/04/21/get_post_put_and_delete_in_rest.html
 [2]: http://naeblis.cx/rtomayko/2005/04/22/on-http-abuse