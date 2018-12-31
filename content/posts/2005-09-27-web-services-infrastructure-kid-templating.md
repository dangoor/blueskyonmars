---
title: 'Web Services Infrastructure: Kid Templating'
author: Kevin Dangoor
type: post
date: 2005-09-27T11:27:45+00:00
url: /2005/09/27/web-services-infrastructure-kid-templating/
categories:
  - Python

---
Ryan Tomayko put up an article describing the genesis of [Kid][1] as an answer for generating responses for web services. Right now, TurboGears produces HTML and JSON as part of the out-of-the-box experience. I definitely expect that we&#8217;re going to see the ability to specify a Kid template for XML output.

I think that toward the end of my time in Javaland, an increasing number of the blogs I read seemed to be doubting WS-\*. The problem with a specs like WS-\* is that when people just sit down to crank out a &#8220;standard API&#8221;, they&#8217;re going to try to take into account _every possible need_. The best APIs I&#8217;ve used, though, are the ones that focus on making the common case as easy as possible, and leaving the door open enough to deal with uncommon issues. These APIs are generally made better because people actually use them.

There&#8217;s a reason that people still use XML-RPC, despite the existence of SOAP. It&#8217;s simple and it gets the job done for a fair number of scenarios&#8230;

 [1]: http://lesscode.org/2005/09/24/web-services-infrastructure-kid/