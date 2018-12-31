---
title: What is a “release candidate”?
author: Kevin Dangoor
type: post
date: 2006-04-26T13:28:40+00:00
url: /2006/04/26/what-is-a-release-candidate/
categories:
  - Software Development

---
There are some software version numbering conventions that people rely on a little bit. 1.1 is newer than 1.0. alpha is less solid than beta. The exact definitions of a move to 1.1 or from alpha to beta are variable from project to project. People do whatever works for their project, and that&#8217;s cool. As long as users can figure out what they&#8217;re downloading and have reasonable expectations, it really doesn&#8217;t matter.

I do have a bit of a pet peeve with the way a number of projects use the term &#8220;release candidate&#8221; (often appearing as &#8220;rc&#8221; in version numbers). Release candidate is very descriptive: it is a candidate for the final release. The idea is that you put the release candidate out there, make sure nothing silly crops up, and then tag _that exact same code_ as the final release. That&#8217;s the whole point of a release _candidate_. That bit of code was thought to have been ready for final release and you&#8217;re just doing a sanity check.

Instead, I&#8217;ve seen projects that introduce fairly significant changes between release candidates. I just saw a project which has had rc6 out for 2.5 months! Release candidates should be followed fairly quickly by the final release (the bigger the project, the more leeway you&#8217;d likely need in the timing). It&#8217;s just hard to envision a need to wait so long and have so many release candidates. Unless, of course, it wasn&#8217;t actually a &#8220;release candidate&#8221; but rather just another beta.

Monkey with &#8220;alpha&#8221;, &#8220;beta&#8221; and &#8220;gamma&#8221; releases all you want, but at least recognize &#8220;rc&#8221; for what it is because it&#8217;s just plain English.