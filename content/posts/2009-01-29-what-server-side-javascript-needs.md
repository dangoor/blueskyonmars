---
title: What Server Side JavaScript needs
author: Kevin Dangoor
type: post
date: 2009-01-29T14:00:00+00:00
url: /2009/01/29/what-server-side-javascript-needs/
categories:
  - JavaScript

---
[Server side JavaScript][1] technology has been around for a _long_ time. Netscape offered server side JavaScript in their server software back in 1996, and [Helma][2] has existed for a number of years as well. But, server side development has changed a lot over the past few years.

Aptana&#8217;s [Jaxer][3] gives an innovative view of how you can leverage a JavaScript environment running on both sides of the wire (client and server). Very convenient communication and the ability to easily share code between client and server are big benefits of running JavaScript on the server.

Jaxer and Helma are interesting projects, to be sure (and there are many others!). But what I see missing from JavaScript on the server is not interesting projects, but rather a useful _ecosystem_. People working in Python like to talk about the fragmentation of web frameworks and whatnot, but that&#8217;s nothing compared to the fragmentation of JavaScript.

For example, JavaScript needs a **cross-interpreter standard library**. Thankfully, some amount of standard library exists (the part inherited from the browsers). So, you get regular expressions and dates. But, what about files and directories? Why can&#8217;t the same API be made to work in Rhino, Spidermonkey, V8 and JSCore?

A handful of **standard interfaces**. Connecting to a database and running queries is a well understood and common problem. In Rhino, you get to use JDBC. But, JavaScript really should have its own cross-interpreter standard like Python&#8217;s [DBAPI][4]. It should also be possible to take a webapp that was originally deployed behind an Apache module running Spidermonkey and then put it behind Jetty thanks to a [standard web server/web app interface][5].

JavaScript needs a **standard way to include other modules** and for those modules to live in discreet namespaces. There are easy ways to do namespaces, but there&#8217;s no standard programmatic way to load a module (_once!_). This is really important, because server side apps can include a lot of code and will likely mix and match parts that meet those standard interfaces.

There needs to be a way to **package up code for deployment and distribution** and further to **install packages**. Linux people will correctly point out that they can just type &#8220;apt get&#8221; (or yum, or whatever) and their work is done. But there are a lot of people using Macs and Windows who need a convenient way to get their development environments set up and to package up the code they write for deployment and for other people to use.

Part of the distribution and installation problem is a **package repository**. I don&#8217;t know if [JSAN][6] is the answer there, but I do know that an easy way to install a package **and its dependencies** makes a huge difference in how many libraries people will likely pull together in their apps.

And, on top of all of this goodness, we&#8217;d get template engines, object relational mappers, middleware, packaged apps, etc. In fact, many of those things already exist. But, the problem is that they have no common basis to sit on. And that&#8217;s what prevents an ecosystem from growing.

If you search the Python Package Index for WSGI (the Python standard for connecting webapps with web servers), you&#8217;ll find 180 packages today&#8230; servers, middleware, full blown applications. And those are just the packages that have &#8220;WSGI&#8221; in their listings. _That&#8217;s_ what an ecosystem looks like. And Java has one, and Ruby has one, and JavaScript needs one.

It&#8217;s also worth noting that many of those WSGI components can run unchanged on CPython, Jython and IronPython, thanks to a common standard library. JavaScript has a collection of implementations in C, as well as Java and .Net implementations and there just needs to be a little agreement on some interfaces and such. Libraries that run in all of those places can attract more users and, hopefully, more committers to help the libraries grow.

What I&#8217;m describing here is not a technical problem. It&#8217;s a matter of people getting together and making a decision to step forward and start building up something bigger and cooler together.

To that end, I&#8217;ve set up a new [ServerJS group][7] in hopes of getting the interested parties talking and maybe even to get us together face-to-face to produce some code and settle on some interfaces. There&#8217;s a tremendous collection of JavaScript code out there already, and let&#8217;s see if we can make all of that code that much more valuable.

In the web developer tools group at Mozilla, we have a wide open charter to help software developers make the best use of the open web. Doing our bit to help the server side JavaScript community grow and flourish can certainly be a part of that.

(Before someone says &#8220;why not just use Ruby/Python/Java/C#?&#8221; let me just say that that is an entirely different question and I won&#8217;t address that in this post.)

**Update:** The group is now called [CommonJS][7].

 [1]: http://en.wikipedia.org/wiki/Server-side_JavaScript
 [2]: http://dev.helma.org/
 [3]: http://www.aptana.com/jaxer
 [4]: http://www.python.org/dev/peps/pep-0249/
 [5]: http://jackjs.org/
 [6]: http://openjsan.org/
 [7]: http://groups.google.com/group/commonjs