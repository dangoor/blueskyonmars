---
title: CherryPy and WSGI
author: Kevin Dangoor
type: post
date: 2006-03-09T16:51:15+00:00
url: /2006/03/09/cherrypy-and-wsgi/
categories:
  - Python
  - TurboGears

---
Christian Wyglendowski posts a great summary of where [CherryPy 2.2 stands with regards to WSGI][1]. If you&#8217;ve followed the discussion on the various mailing lists and thought CherryPy only minimally handled WSGI, this post does a great job of setting the record straight. CP2.2&#8217;s WSGI support is not 100% ideal, but it&#8217;s _way_ better than 2.1 and you can do an awful lot with it. Big kudos to Christian, Robert Brewer, Ian Bicking and Phillip Eby for hashing it out and coming up with an implementation that meets CherryPy&#8217;s backwards compatibility needs and takes a big step forward.

As Ian mentioned in his [PyCon 2006 wrapup][2], we ran an experiment during the TurboGears sprint to see what TurboGears looks like built entirely on a WSGI stack. It actually looks pretty cool. There are lots of nifty application composition possibilities and quite a number of ways to share code with other projects. Something I wasn&#8217;t aware of heading in to PyCon was Christian&#8217;s filter that allows you to attach other WSGI apps to your CherryPy object tree. With that capability, it should become possible to do everything that we could do with our experimental branch using CherryPy 2.2.

This leads to really interesting questions on how to proceed with the post 1.0 TurboGears release that will have these features. (This fabulous release is code named &#8220;First Class&#8221; and appears in a branch called firstclass in the repository.) There are always tradeoffs. The one thing is certain: First Class uses WSGI in a big way, and I&#8217;m really looking forward to the possibilties.

Discussion of First Class will take place on the new [turbogears-trunk][3] mailing list that will be used for discussing unreleased code.

 [1]: http://blog.dowski.com/2006/03/08/cherrypy-and-wsgi-can-play-nice/
 [2]: http://blog.ianbicking.org/pycon-2006.html
 [3]: http://groups.google.com/group/turbogears-trunk