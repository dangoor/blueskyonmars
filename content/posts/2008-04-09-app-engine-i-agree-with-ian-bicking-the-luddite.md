---
title: 'App Engine: I agree with Ian Bicking the Luddite'
author: Kevin Dangoor
type: post
date: 2008-04-10T01:17:48+00:00
url: /2008/04/09/app-engine-i-agree-with-ian-bicking-the-luddite/
categories:
  - Python
  - Software Development
tags:
  - app engine
  - aws
  - google

---
Isn&#8217;t quoting out of context great:

<blockquote cite="http://blog.ianbicking.org/2008/04/09/app-engine-commodity-vs-proprietary/">
  <p>
    I hate computers.<br /> [From <a href="http://blog.ianbicking.org/2008/04/09/app-engine-commodity-vs-proprietary/"><cite>Ian Bicking: App Engine: Commodity vs. Proprietary</cite></a>]
  </p>
</blockquote>

More seriously, though, in saying &#8220;I hate computers&#8221;, Ian is actually talking about the opposite of being a Luddite. He&#8217;s dreaming of a world in which much of computing just works in the background, so that we can spend our time doing more important and interesting things in the foreground.

I&#8217;m linking to Ian here because he&#8217;s said exactly what I have been thinking about [App Engine][1]: from a Python programming perspective the APIs are simple and clear. I can easily imagine a ZODB-based implementation of Google&#8217;s data store API. Just change your imports, and you can be off of Google&#8217;s infrastructure and on to your own.

Of course, for a great many people there won&#8217;t be any reason to be off of Google&#8217;s infrastructure. App Engine is just <span style="font-style: italic;">so darn easy</span>. Amazon Web Services is impressive because it makes scalability affordable and available. App Engine interests me because, for its broad-but-still-limited set of use cases, it makes scalability a no brainer. &#8220;Build your app like this, and you never have to think of scaling&#8221; is a nice thought. I&#8217;ve been around enough to know that people using App Engine will still have to think of scaling <span style="font-style: italic;">some</span>, but not nearly as much as with just about any other solution.

Back to the lock-in aspect, though. I still see App Engine as likely to be utterly unsuccessful with large businesses. That is, until a new Google Appliance comes out. I&#8217;ve been predicting such a beast since Google Docs was first introduced, and I think App Engine makes it all the more likely. I still believe that there will come a time when Google will sell boxes to big companies that those companies can toss into some racks on their networks and deploy App Engine apps locally, as well as run Google Docs on their private nets. Things will get even more interesting at that point.

You can bet that Amazon is studying App Engine closely and considering their own high-level service as I write this. From a developer&#8217;s perspective, this competition is going to be awesome.

 [1]: http://appengine.google.com/