---
title: 'Paver 0.7: Better than distutils, better docs and much more'
author: Kevin Dangoor
type: post
date: 2008-05-08T02:55:29+00:00
url: /2008/05/07/paver-07-better-than-distutils-better-docs-and-much-more/
aktt_tweeted:
  - 1
categories:
  - Python
tags:
  - Paver

---
I&#8217;m delighted to release [Paver][1] 0.7. If you missed my [original announcement][2], the short story is that Paver is a new build, distribution and deployment scripting tool geared toward Python projects. My original announcement and the [new foreword][3] to the docs explain the motivation.

Ben Bangert and others pointed out a giant documentation bug in 0.4: there was a fair bit of reference doc but no doc that said &#8220;here&#8217;s how you get started with Paver&#8221;. Now there is: Paver&#8217;s [Getting Started Guide][4].

Paver 0.7 is a big step up from 0.4 (hence the version number bump). I implemented one of the two major features I had planned for 1.0: distutils/setuptools integration. It&#8217;s really cool. Have you ever wanted to just slightly change how &#8220;sdist&#8221; or &#8220;upload&#8221; or &#8220;develop&#8221; worked? Now you can, just by writing a function in your pavement.py file. And don&#8217;t worry, you don&#8217;t need to duplicate anything between setup.py and pavement.py. It all just moves into pavement.py and Paver can even generate a setup.py file for you, since most people are use to the common &#8220;python setup.py install&#8221; command.

I&#8217;ve gone even farther than that with making it easy to use Paver and not annoy users that don&#8217;t yet have Paver. Paver can create a small zip file of Paver&#8217;s core bits so that &#8220;python setup.py install&#8221; will work just fine even for users who don&#8217;t have Paver installed. Paver can also create a virtualenv bootstrap script for you, so that users don&#8217;t necessarily need to install your package on their systems in order to use it.

Paver&#8217;s got new documentation tools that work great with Sphinx. It&#8217;s now easy to mark sections of sample code files and then include those sections in your documentation, using the built-in version of Ned Batchelder&#8217;s [Cog][5].

And I&#8217;m definitely eating my own dogfood. Paver is built using Paver itself and the source distribution includes the paver-minilib so that setup.py install should work fine (let me know if it doesn&#8217;t!) The new Getting Started Guide uses the new documentation tools.

There are even more changes than these, and you can look at the [changelog][6] for the full list. Note that if you&#8217;re using Paver 0.4, there are a couple of trivial breaking changes.

 [1]: http://www.blueskyonmars.com/projects/paver/
 [2]: http://www.blueskyonmars.com/2008/04/22/paver-and-the-building-distribution-deployment-etc-of-python-projects/
 [3]: http://www.blueskyonmars.com/projects/paver/foreword.html
 [4]: http://www.blueskyonmars.com/projects/paver/getting_started.html#gettingstarted
 [5]: http://nedbatchelder.com/code/cog/index.html
 [6]: http://www.blueskyonmars.com/projects/paver/changelog.html#may-7-2008