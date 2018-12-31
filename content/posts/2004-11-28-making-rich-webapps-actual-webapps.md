---
title: Making rich webapps actual webapps
author: Kevin Dangoor
type: post
date: 2004-11-29T02:53:44+00:00
url: /2004/11/28/making-rich-webapps-actual-webapps/
categories:
  - Software Development

---
I was going to write a follow-up to Scott Delap&#8217;s [rich webapp rant][1], but it turns out that Frank Carver <a title="Frank Carver's weblog - Worries about "rich web applications"" href="http://radio.javaranch.com/channel/frank/2004/11/28/1101660825000.html">has already written it</a>. There are a number of things that creating a webapp gives you &#8220;for free&#8221;: back/forward, printing (of _everything_), bookmarks, URL cut/paste, reload/stop, etc. People like these features. In fact, the Swing app I&#8217;ve been working incorporates a few of these features, because they represent a minimum set of functionality that people have come to expect.

Frank makes great points, though. There are good reasons to create rich webapps. If you do, make sure that the thing still behaves like a webapp. It&#8217;s good to remember things like bookmarks, while making a webapp that reduces &#8220;server round-trips&#8221;. For example, in gmail, maybe I&#8217;d like a bookmark to a conversation&#8230; as far as I can tell, I can&#8217;t do that. (Why would I want a bookmark to a conversation with such great search features? Beats me&#8230; so, maybe it&#8217;s a trumped up use case.)

Even if the gmail example is not valid, I&#8217;m sure there are plenty that are. Imagine a customer relationship management app. If a salesperson is working with one particular customer a lot, they may wish to bookmark the main contacts page for that customer for quick access. That seems like a good feature to have, and it&#8217;s one the browser gives you for free, if you don&#8217;t try to work around its standard mechanisms.

 [1]: http://www.clientjava.com/blog/2004/11/26/1101491234000.html