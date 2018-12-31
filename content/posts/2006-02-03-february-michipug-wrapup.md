---
title: February MichiPUG wrapup
author: Kevin Dangoor
type: post
date: 2006-02-03T18:37:20+00:00
url: /2006/02/03/february-michipug-wrapup/
categories:
  - Python

---
Last night was the February meeting of the [Michigan Python Users Group][1]. As usual, it was a good, lively meeting. We had a presentation from Jim MacDonald on [setuptools][2]/Easy Install/Python Eggs, which led to an inevitable discussion about packaging tools and systems. Everyone seemed pleased at what setuptools brings to the picture (and I&#8217;ve been a big fan for several months).

We had another presentation from Steve Kryskalla which covered a very interesting project: converting a Chinese teaching web site to Python. The really intriguing part of his project is that the content of the existing site was _all in images_! With the help of [PIL][3] and [pyparsing][4], he wrote a &#8220;proto-OCR&#8221; tool that pulled the content out and turned it into a domain specific language for the data on this website. He&#8217;s gone through a bunch of cleanup work and is starting to work on the real site (in [TurboGears][5]). Nifty project, and I&#8217;m glad Steve shared it!

Next month&#8217;s meeting has moved to Tuesday, March 7th since Mark (our host) and I will be in Dallas for PyCon and the TurboGears sprint.

Update: in addition to misspelling Steve&#8217;s last name, I also forgot to mention the always entertaining after-meeting discussion. We spoke for a while about RDF and, independently, the new Python.org site. Jim promises a future talk on RDF that should be interesting.

 [1]: http://www.michipug.org/
 [2]: http://peak.telecommunity.com/DevCenter/setuptools
 [3]: http://www.pythonware.com/products/pil/
 [4]: http://pyparsing.sourceforge.net/
 [5]: http://www.turbogears.org