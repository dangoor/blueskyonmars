---
title: The magical, mystical “1.0”
author: Kevin Dangoor
type: post
date: 2005-10-04T15:22:03+00:00
url: /2005/10/04/the-magical-mystical-10/
categories:
  - Software Business
  - TurboGears

---
It seems that many open source projects don&#8217;t want to put themselves at the magical &#8220;1.0&#8221; number until the software is &#8220;done&#8221;. In my opinion, software is &#8220;done&#8221; when it reaches its end of life and is being put out to pasture. That&#8217;s one of the great things about software: it&#8217;s malleable! Software is much more malleable that many other &#8220;products&#8221;.

One could start a project by declaring &#8220;SuperMegaWidget will be called 1.0 once it has found a cheap, renewable, clean energy source&#8221;. That may sound outlandish, and it is, but quite a few projects set the bar very high for 1.0.

Maybe this is some new breed of 1.0 that is different from the kind I grew up with in the &#8217;80s. Do you remember Windows 1.0? It was not pretty or useful. It couldn&#8217;t even stack windows (they were all tiled). But, it was a starting point and it _did what it said on the box_.

These days, it seems like everyone coming out with an MP3 player starts it off at 0.1 saying &#8220;well, it only plays MP3s&#8230; I&#8217;ll call it 1.0 once it plays Ogg, MPEG video, protected WM files and can transparently connect to P2P networks to download other songs you might like&#8221;. That&#8217;s crazy! If you&#8217;ve bothered to package up a release at all, clearly you think there&#8217;s something cool and useful there. Give it a proper starting point. Call it 1.0.

One might make the argument that, with programming tools and libraries, you can&#8217;t just make changes willynilly after 1.0 because people are depending on the stability of the API for their own products. The fact is that after a project becomes useful and has a community, you&#8217;re already _somewhat_ locked in to the API you&#8217;ve provided. If you&#8217;re not prepared to at least document API changes, _don&#8217;t make a release_. Just leave it in Subversion, which makes it really obvious that you&#8217;re likely to change anything at a moment&#8217;s notice.

1.0 doesn&#8217;t mean &#8220;changes are no longer allowed&#8221; or even that &#8220;changes are hard&#8221;. It does mean that anything that might break a user&#8217;s code should

  * Preserve backward compatibility where possible (and not too heinous)
  * Be documented
  * Have a suitable deprecation period for things that are going away

These requirements are not too onerous. [Python][1] and [Java][2] have grown this way. They don&#8217;t grow quickly, but I think that&#8217;s partly in the nature of the tools. Different packages will be able to change at different rates. It&#8217;s especially easy to document and assist with backwards incompatible changes if you [keep track of them as you implement them][3].

Languages like Python that offer keyword function/method parameters and duck typing make it even easier to maintain backwards compatibility while providing new features.

For [TurboGears][4], I started it at 0.5 knowing that such a web development package could use some more outside review and validation before the APIs could be thought of &#8220;stable&#8221;. I also knew, [and said][5] that it would quickly reach 1.0. TurboGears parts were all solid and fairly mature, and it was really only the glue that needed some review.

Even I&#8217;m somewhat guilty of 1.0-itis. The forthcoming [TurboGears 0.8][6] release could be called 1.0, assuming the requirements on that development status page are met. I knew that the sprint was coming very soon, though, so I decided that we may as well get the sprint results merged in to the final 1.0 release.

So, I say &#8220;embrace 1.0!&#8221; And then get back to work, because 1.0 is just the beginning.

 [1]: http://www.python.org
 [2]: http://java.sun.com
 [3]: http://www.turbogears.org/svn/turbogears/trunk/CHANGELOG.txt
 [4]: http://www.turbogears.org
 [5]: http://www.turbogears.org/about/status.html
 [6]: http://trac.turbogears.org/turbogears/roadmap