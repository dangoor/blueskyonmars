---
title: URL-rewriting in CherryPy 2.1 and TurboGears
author: Kevin Dangoor
type: post
date: 2005-10-27T13:15:33+00:00
url: /2005/10/27/url-rewriting-in-cherrypy-21-and-turbogears/
categories:
  - Python
  - TurboGears

---
Robert &#8220;FuManChu&#8221; Brewer goes in-depth on [URL-rewriting in CherryPy 2.1][1]. This is some documentation I wish I had a couple weeks ago. Robert sums up which aspects of mounting apps at arbitrary points are broken:

> 1. Generating URL&#8217;s to spit back out in HTML. Broken. I now have to manually provide prefix to my HTML templates, or take on the nightmare of making every generated URL into a URL which is relative (e.g. &#8220;../../otherpage&#8221;) to the current one.
> 
> 2. HTTP Redirects and their targets. Broken. I now have to manually provide prefix to each instance (or use relative URL&#8217;s). But I can&#8217;t control CherryPy&#8217;s redirect instances! For example, when CherryPy tries to redirect index methods by adding a trailing slash to the requested URI, it uses the value of path, which I&#8217;ve rewritten.
> 
> 3. Handler dispatch: not broken.
> 
> 4. Arbitrary mount points: not broken.
> 
> 5. Config lookups. Broken? Some other filter which does a config lookup could run their onStartResource method before mine. Since my filter is user-defined, it is forced to run after all of the builtin ones; none of those currently perform config lookups, however. If any of the server.* config entries are specified somewhere other than &#8220;global&#8221;, then we have the same issue. Finally, what&#8217;s to stop a future CP developer from adding more such problems (as they fix other bugs)?
> 
> 6. Logging: the error.log and access.log will both use the original URI (from requestLine). Broken? or not? One? Both? 

I should note that TurboGears has a fix for #1 and #2 on the list, in the form of an included URL generation function that takes the application root into account. #2 is actually only partly fixed by the URL function. CherryPy&#8217;s built in trailing slash redirect knows nothing about my little URL function. There&#8217;s a ticket open in the TurboGears Trac about static resources in mounted apps that is basically consideration #5 on Robert&#8217;s list. I hadn&#8217;t looked at the logging aspect of the problem, so I&#8217;ll definitely take Robert&#8217;s word on the state of it.

 [1]: http://www.aminus.org/blogs/index.php/fumanchu/2005/10/27/url_rewriting_in_cherrypy_2_1