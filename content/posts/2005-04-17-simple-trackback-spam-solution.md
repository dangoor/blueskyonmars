---
title: Simple trackback spam solution
author: Kevin Dangoor
type: post
date: 2005-04-18T05:17:11+00:00
url: /2005/04/17/simple-trackback-spam-solution/
categories:
  - Technology

---
This has got to exist already. Today, I was battling trackback spammers. I have MT-Blacklist installed, so they&#8217;re mostly just a nuisance, because I have to delete and rebuild all of those entries that they hit. 

Then it occurred to me: all of the trackback spam that I have seen has been repeated multiple times on the blog. They never hit just one post, and they&#8217;ll often hit dozens or maybe even hundreds.

So, at least for now, a simple solution would be to compare the received trackback with the last N trackbacks to see if there are URLs in common. If so, consider them spam and waste them. I don&#8217;t think there&#8217;s any legitimate reason to receive the same trackback repeatedly.

Of course, this won&#8217;t last forever, because if everyone does this the trackback spammers will just make every URL unique. You can&#8217;t work stricly off of the domain provided because of sites like blogspot and typepad. It is conceivable that a popular blog will get more than one trackback from one of these sites within a short period of time.

I would consider implementing this myself, but I&#8217;m going to change blog software soon. I&#8217;m leaning toward WordPress right now, because it looks pretty slick.