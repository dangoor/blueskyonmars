---
title: Over GPLed
author: Kevin Dangoor
type: post
date: 2006-03-03T22:03:40+00:00
url: /2006/03/03/over-gpled/
categories:
  - Software Business

---
Last week, it was a Python [template engine][1]. This week, it&#8217;s [JavaScript tabs library][2]. It seems to be a fairly common occurrence that people release developer-oriented open source packages that come with a GPL license. Unless you intend to create a business selling your software with a different license to business (the Sleepycat model), this just seems like a way to severely restrict use of your library. The only people likely to use libraries like those that are licensed under the GPL license are people that are writing open source (GPL) applications. If that&#8217;s what you want, fine&#8230; but, I think it&#8217;s better to aim higher. (In case you read no further, those two packages have since relicensed under MIT style licenses.)
  
I understand the allure of the GPL. &#8220;I&#8217;ve put this thing out there for free, and so I should benefit from the changes other people made!&#8221; (I&#8217;m ignoring the &#8220;software should be free&#8221; philosophical argument for now.) I think it&#8217;s a mistake to think that just because something is released under a liberal license, like the [MIT license][3] which is what I use, that companies won&#8217;t contribute their changes back to the project.

Creating a fork of a project is a pain. You have to reintegrate changes every time there are improvements in the core project that you want to take. For a company to maintain their own internal version of your project effectively means that they have their own fork of it. That just doesn&#8217;t make good business sense. A company _could_ choose to take your project and produce some spiffy commercial version. Odds are, though, that they&#8217;d still release changes to the core system back to the project, rather than maintaining a private fork.

I think that most people who choose the GPL for a library do so because it&#8217;s a license they&#8217;re familiar with. That&#8217;s the point of this post: hopefully, more people creating libraries will recognize that a very liberal license like MIT or BSD is the way to win users. The authors of both of the projects that I mention above have agreed to relicense under MIT-style licenses!

I should also point out that the LGPL is somewhat ambiguous when it comes to dynamic languages. If you really want a license that requires the open source release of changes on a library that you&#8217;re releasing, you should think about the Mozilla Public License. (**Update**: The [CDDL][4] appears to be a version of the MPL that is designed to be more easily reused. That&#8217;s a good one to consider.) That license is not vague: only the files in your distribution are required to remain under the MPL. So, the code is free to use for commercial purposes, but any changes to the files that you distributed also need to be released under the MPL. I&#8217;d still recommend going with an MIT license in general, but at least the MPL is clear in its effects.

By the way, I have no problem with using the GPL for applications. Applications released under the GPL can be used for all kinds of purposes, and it&#8217;s reasonable to want changes to the application to be similarly licensed.

**Update**: I eliminated the use of the word &#8220;viral&#8221; above, because I didn&#8217;t intend to make a negative point on the use of licenses that impose restrictions on distributed versions of software. My point is that many choose these licenses without being fully aware of the ramifications.

It is also clear from the comments that I never got back to the &#8220;software should be Free&#8221; (software libre) argument.

As mentioned in the comments, not everyone is looking for the broadest possible adoption of their code. Some people specifically have the belief that all software should be free to use, upgrade and share. People are certainly free to have and exercise that belief by licensing their software under the GPL. If I asked someone to relicense and they told me that they chose GPL to ensure freedom of the software, I wouldn&#8217;t argue any further. Those people have chosen the GPL for the right reasons.

The fact that I have spoken with two people in the past two weeks who relicensed their software shows that there _are_ people out there choosing the GPL for reasons other than support of software libre.

 [1]: http://manatlan.online.fr/hypy.php
 [2]: http://www.barelyfitz.com/projects/tabber/index.php
 [3]: http://www.opensource.org/licenses/mit-license.php
 [4]: http://www.opensolaris.org/os/about/faq/licensing_faq/#whatis