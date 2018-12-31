---
title: Google AJAXSLT
author: Kevin Dangoor
type: post
date: 2005-06-24T16:45:11+00:00
url: /2005/06/24/google-ajaxslt/
keywords:
  - programming,xml,ajax,javascript
categories:
  - Software Development

---
The new [Google AJAXSLT][1] provides a JavaScript XSL-T and XPath implementation that you can use when providing AJAX goodness in your apps. It&#8217;s licensed under a BSD-style license, so you can use it for whatever you want.

As you can see from the [readme][2], Google had to really work to smooth out differences between browsers, many of which have no exposed XSL or XPath functionality at all. As you can guess, it&#8217;s probably not going to be whizzy fast if your browser doesn&#8217;t have built-in XSL.

Personally, I have a strong dislike for XSL&#8217;s syntax. Though it&#8217;s not declarative or as &#8220;technically pure&#8221;, I prefer the syntax of something like [TrimPath JavaScript Templates][3]. And I bet TrimPath&#8217;s templates are applied more quickly.

 [1]: http://goog-ajaxslt.sourceforge.net/
 [2]: http://goog-ajaxslt.sourceforge.net/README
 [3]: http://www.trimpath.com/project/wiki/JavaScriptTemplates