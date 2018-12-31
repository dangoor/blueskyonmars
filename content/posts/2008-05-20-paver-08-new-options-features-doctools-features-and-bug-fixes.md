---
title: 'Paver 0.8: new options features, doctools features and bug fixes'
author: Kevin Dangoor
type: post
date: 2008-05-21T02:28:39+00:00
url: /2008/05/20/paver-08-new-options-features-doctools-features-and-bug-fixes/
aktt_tweeted:
  - 1
categories:
  - Python
  - TurboGears
tags:
  - Paver

---
For various reasons, I released [Paver][1] 0.7.3 on Friday and Paver 0.8 yesterday. I have an idea of what the coming 1.0&#8217;s zc.buildout integration will be like, and I think it will be quite cool and useful.

In the meantime, though, I&#8217;ve got some new features that set the stage for things I need to do in 1.0. Specifically, you can now pass in a dictionary in your options search ordering. So, you can pull options from any source you&#8217;ve got at the time the task is running and stick them at the front of the line. I expect to use this in buildout options handling.

A nice new feature is the ability to set options on the command line. You can do something like:

> <pre>paver some.option=hello task1 some.option=goodbye task2
</pre>

Doing that, paver will set some.option to hello, run task1 and then change the option to goodbye before running task2.

The new cog.include\_markers and cog.delete\_code options allow you to remove Cog&#8217;s markers from the output and instead put a nicer bit of text to say where the snippet of code came from. Letting the user know where a sample code snippet came from is quite valuable, so I want to make it possible to do so in as pleasing a way as possible.

For [Paver&#8217;s Getting Started Guide][2], I ended up not using the new include_markers feature and instead just changed the Cog delimiters. I did this because Paver runs shell commands in addition to including file sections when generating the docs. I wanted those shell commands to be included. I think the new markers are more pleasant to look at, and I&#8217;ll be curious to get feedback since I heard from more than one person that the Cog delimiters looked like they were left in by mistake.

Paver is starting to get some traction as it has picked up its first patches from outsiders, and I&#8217;ve started to get some feedback on breakage from Windows users (fixed in 0.8). [Mark][3] let me put Paver into [TurboGears 2][4], and I think it will help out there, so that will introduce quite a number more people to the project. As always, come and [join us on the mailing list][5] if you have any questions or problems!

 [1]: http://www.blueskyonmars.com/projects/paver/
 [2]: http://www.blueskyonmars.com/projects/paver/getting_started.html
 [3]: http://compoundthinking.com/blog/
 [4]: http://compoundthinking.com/tg2/
 [5]: http://groups.google.com/group/paver/