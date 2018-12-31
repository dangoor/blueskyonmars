---
title: ZCatalog for standalone ZODB
author: Kevin Dangoor
type: post
date: 2005-06-07T13:03:22+00:00
url: /2005/06/07/zcatalog-for-standalone-zodb/
categories:
  - Python

---
I have just packaged up [ZCatalog from Zope 3.1][1] for use with the standalone ZODB. I&#8217;m surprised that no one had released this previously, because all but the most trivial of ZODB apps will need some way to do non-primary key sorts of searches.

Previously available solutions that I spotted are: \[IndexedCatalog\](http://www.async.com.br/projects/IndexedCatalog/) and \[these instructions for getting Zope 2.6&#8217;s ZCatalog working\](http://slarty.polito.it:8069/~sciasbat/wiki/moin.cgi/StandaloneZodbHowto).

The major feature that ZCatalog has over IndexedCatalog is a full-text search index.

I had originally packaged up the Zope 2.8 catalog. That was generally working, but I wasn&#8217;t completely comfortable with it because the code was fairly &#8220;tangled up&#8221;. The Zope bits were spread throughout the code. Zope 3 has a beautiful architecture, and extracting the catalog from there was far easier.

Note, however, that this means that current ZCatalog plugins (\[Dieter Maurer&#8217;s AdvancedQuery\](http://www.dieter.handshake.de/pyprojects/zope/#AdvancedQuery), or \[TextIndexNG\](http://www.zopyx.com/OpenSource/TextIndexNG), for example) won&#8217;t work directly. Hopefully, it will not be difficult to get these sorts of things running. Generally speaking, that is left as an exercise to the reader (patches accepted 🙂

I&#8217;m calling this release 1.0 alpha 0, because the testing that I&#8217;ve done is approximately as extensive as what you see in the readme file. Which is to say that it passes the most basic of sanity checks, but I haven&#8217;t looked much beyond that. I&#8217;ll be exercising it a lot more this week, so I&#8217;ll probably have a bit more confidence later.

When it comes to developer tools, though, release early, release often is a good motto.

 [1]: http://www.blazingthings.com/zcatalog