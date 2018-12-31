---
title: A day after TurboGears’ release
author: Kevin Dangoor
type: post
date: 2005-09-19T03:47:27+00:00
url: /2005/09/18/a-day-after-turbogears-release/
categories:
  - Python
  - TurboGears

---
[TurboGears][1] had a quiet launch on Wednesday, when I presented the &#8220;20 Minute Wiki&#8221; live at the first MichiPUG meeting. It was listed as just &#8220;CherryPy+SQLObject&#8221; on the agenda, since TurboGears hadn&#8217;t been announced in any form at that point.

Yesterday, I made the more public announcement here on Blue Sky On Mars and on python-announce. From previous experience, it seemed like things tended to be a bit quieter on the weekends. It turns out that Python people were watching, even on Saturday. And, it also turns out that Python people are still very interested in web toolkits!

In a little more than a day, the [&#8220;20 Minute Wiki&#8221;][2] screencast has been viewed more than 1,000 times. That&#8217;s rather startling for my first screencast. By the way, I should take this opportunity to correct a problem with my screencast: I pronounced &#8220;MochiKit&#8221; wrong. [Bob Ippolito][3] pointed out that &#8220;mochi&#8221; is a Japanese word that is pronounced MOH-chee.

Bob, in addition to creating the fabulous MochiKit, also gets credit as the first person to submit code to TurboGears: a nifty snippet for doing Bonjour (formerly Rendezvous aka zeroconf) advertisements of the project you&#8217;re working on. [Phillip Eby][4] gets credit as the first person other than me to respond to a question on the TurboGears mailing list. I&#8217;m glad he did, because he was able to go into some detail about installing Python Eggs when you already have some of the packages installed.

On the TurboGears mailing list, it sounds like Windows and Mac users have been having good success with the Easy Install, but that Linux users have been having a harder time. ASAP, I&#8217;m going to write another install doc to deal with some of the complexities that can come up. Eggs are a great tool for Python and the solve a number of problems, so they&#8217;re well worth the little bit of extra trouble involved right now until they become the norm.

Out on the web, there were several blog posts talking about TurboGears. Bob [said][5]:

> There&#8217;s a lot of good first impressions to be had with the technology

And he enumerated some of the reasons why I like the projects that I chose for TurboGears. As a Twisted fan (and contributor), he&#8217;d like to see it running behind Twisted. That would be difficult with SQLObject, which is synchronous, because Twisted is asynchronous.

Phillip [said][6]:

> Okay, so TurboGears is cool. Not because it&#8217;s another Python web framework, but because it&#8217;s a&#8230; megaframework? Okay, so it&#8217;s not a framework, but what the heck is a megaframework?
> 
> Not that I have a better name for it, mind you. It is definitely a new thing in the Python world &#8211; a compelling project built almost entirely from separately-packaged Python components, powered by setuptools and EasyInstall.

EasyInstall is a key piece of technology to make something like TurboGears fly. If Phillip hadn&#8217;t created it (and done such a fine job of it!), I would have had to create some far less pleasant and less powerful mechanism to make TurboGears installable for people who don&#8217;t have an afternoon to waste tracking down dependencies.

It&#8217;s late for me now, so I&#8217;m going to have to continue checking out and commenting on the responses another time. I appreciate the early interest and I&#8217;m really excited about the parts that are yet to come!

 [1]: http://www.turbogears.org/
 [2]: http://www.turbogears.org/docs/wiki20/
 [3]: http://bob.pythonmac.org/
 [4]: http://dirtsimple.org
 [5]: http://bob.pythonmac.org/archives/2005/09/17/turbogears/
 [6]: http://dirtsimple.org/2005/09/whats-megaframework.html