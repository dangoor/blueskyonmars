---
title: What I want in a Wiki for software development
author: Kevin Dangoor
type: post
date: 2005-09-27T19:32:03+00:00
url: /2005/09/27/what-i-want-in-a-wiki-for-software-development/
categories:
  - Product Management
  - Software Development

---
There are lots of wiki programs out there. I mean _lots_. It seems like <a href="http://www.turbogears.org/docs/wiki20/index.html" target="_blank">everyone</a> has written one, in just about every language there is.

Wikis are used a lot for software project documentation, because they&#8217;re just so easy. The barriers to jumping into a wiki and adding a page where one seems needed are so low that people dive right in with gusto. You&#8217;d think that my issue with wikis is that you end up with a huge mass of disorganized pages. That&#8217;s not it, though&#8230; with some judicious care, that mass can be turned into something useful readily enough.

My issue with wikis for software development is a problem of _unknown obsolescence_. The best example of this I can highlight right now is the <a href="http://www.cherrypy.org/wiki/CherryPyRecipes" target="_blank">CherryPy wiki</a>. There&#8217;s quite a bit of potentially useful material there, but almost all of it won&#8217;t work as written in CherryPy 2.1. You go to the wiki looking for info, and you have no idea when you see a given page whether it&#8217;s applicable for the version of the software you&#8217;re using.

<a href="http://www.turbogears.org" target="_blank">TurboGears</a> documentation is all in Subversion because of this. This allows the documentation to naturally be tied to the version of the software. This also has the advantage that I can use my favorite editor and take full advantage of HTML when I&#8217;m doing docs.

Unfortunately, though, I don&#8217;t think anyone is going to check out the project just to write up some new docs. People are a lot more likely to add documentation if it&#8217;s as easy to do as updating a wiki.

We _could_ try to give wikis branching and merging capabilities like you find in source control systems. We could also require users to go through a root canal to view our docs and see how well that goes over. Even though tools have gotten better than they were, branching and merging still seems to be a black art for many.

Perhaps there&#8217;s a simplified user interface that will do the trick. Something like this:

  * By default, a user will be browsing at the latest released version (something that is marked by an admin). Links at the top of the page will let the user choose a different version to browse.
  * Only major versions would get their own version of the wiki. In most software projects, the difference between 2.0 and 2.0.1 doesn&#8217;t involve a whole bunch of potentially breaking changes.
  * When a new version is created, the wiki _starts out empty_. This is important, because it needs to be very clear to someone when they may be viewing a page that is out of date.
  * If a wiki word is referenced that exists in a previous version of the software but not the current, the user can choose to start with the previous version and work from there. This way, there is a manual review step for each page.
  * The history for the &#8220;2.0&#8221; versions of a page is a separate line than the history of the &#8220;2.1&#8221; versions of a page. Usually, the documentation for an older version is just going to languish anyhow.

To me, this seems easy to use for a browser of the wiki, editor of the wiki and even for the creator of the wiki software. Sure, a big wiki with lots of pages will have a bit of pain for a major new release, but you&#8217;re only talking about a couple clicks per page for pages that don&#8217;t require any changes. It seems like a major release is a good time to review the docs.

A decent wiki with a feature like this would definitely make me move my docs out of Subversion. Let me know if one exists.