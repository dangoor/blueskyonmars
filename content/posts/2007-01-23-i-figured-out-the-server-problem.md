---
title: I figured out the server problem.
author: Kevin Dangoor
type: post
date: 2007-01-23T10:25:30+00:00
url: /2007/01/23/i-figured-out-the-server-problem/
categories:
  - Random

---
Or, at least, I think I did. On the old server &#8220;top&#8221; never really showed me much, even when the load was 18+. On the new box, top showed me a pretty even split between MySQL and PHP. The new box was somewhat responsive even under the high load, so I poked around at a mysqladmin processlist and the www_access log file a little bit. It quickly became clear that I was under attack by comment spammers. I updated to the newly released WordPress 2.1, turned off a few plugins that I&#8217;m not really using, and seem to have gotten things to a better place. Let me know if you find the site unresponsive&#8230;