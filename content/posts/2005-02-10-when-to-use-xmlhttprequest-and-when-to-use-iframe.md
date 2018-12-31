---
title: When to use XMLHttpRequest and when to use IFrame
author: Kevin Dangoor
type: post
date: 2005-02-10T19:46:11+00:00
url: /2005/02/10/when-to-use-xmlhttprequest-and-when-to-use-iframe/
categories:
  - Software Development

---
Joel Webber dissects maps.google.com in [Mapping Google][1]. He spent a good deal of time getting into what all is being done by Google Maps. Here&#8217;s an interesting takeaway:

> I mentioned before that there was some advantage to be had by using a hidden IFrame over making direct XMLHttp requests. One of these is that the IFrame&#8217;s state affects the back button. So every time you do a search, it creates a new history entry. This creates an excellent user experience, because pressing the back button always takes you back to the last major action you performed (and the forward button works just as well).

This leads to a good rule of thumb. If you&#8217;re updating the page with new or updated information, you most likely don&#8217;t want a history event. So, use XMLHttpRequest. On the other hand, if you&#8217;re working in resposne to a user request, it would often be better to use the IFrame approach in order to preserve back button behavior.

 [1]: http://jgwebber.blogspot.com/2005/02/mapping-google.html "as simple as possible, but no simpler: Mapping Google"