---
title: How to move a feed
author: Kevin Dangoor
type: post
date: 2005-06-28T14:31:35+00:00
url: /2005/06/28/how-to-move-a-feed/
keywords:
  - rss
categories:
  - Technology

---
So, I just happened to notice that the [Google Blog][1] has moved. I hadn&#8217;t been paying very close attention, because I think it moved a while ago.

In doing the move of their blog, Google did the right thing by putting an HTTP response of 301 &#8211; &#8220;permanent redirect&#8221;. That&#8217;s swell. However, they appear to have done a blanket redirect of the whole blog to the front page of the new blog. That&#8217;s a nice, easy solution&#8230; the only problem is that their old feed

http://www.google.com/googleblog/atom.xml

redirects to the front page of the new blog location, not the new feed. Anyone with a feed reader pointed there, would start having some trouble.

So, the right thing to do when moving your blog (and I&#8217;m pretty sure I did this all properly when I migrated from Movable Type to WordPress) is to do a 301 redirect from your old feed to your new feed. Feed readers will pick that up automatically and you&#8217;ll notice no difference.

If you use Apache, you can just toss a line in your .htaccess file that looks something like this:

Redirect permanent /index.xml http://www.blueskyonmars.com/feed/

That line will redirect any requests for index.xml to my new feed location.

 [1]: http://googleblog.blogspot.com/