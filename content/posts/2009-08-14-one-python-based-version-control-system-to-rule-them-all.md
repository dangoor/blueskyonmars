---
title: One Python-based version control system to rule them all!
author: Kevin Dangoor
type: post
date: 2009-08-15T02:35:31+00:00
url: /2009/08/14/one-python-based-version-control-system-to-rule-them-all/
categories:
  - Bespin
  - Python

---
We&#8217;ve just [released Bespin 0.4][1], the major new feature of which is the first bit of the [collaboration][2] feature. Bespin 0.4 includes a ton of other changes, including one that I&#8217;m going to focus on here: Subversion support, which [Gordon P. Hemsley kicked off for us][3] a few weeks back.

Bespin&#8217;s initial version control support showed up in 0.2 with support for Mercurial. Knowing that we wanted to support multiple version control systems (VCS), I took an unorthodox approach from the beginning. Rather than providing the &#8220;hg&#8221; commands that people know and love, I created a separate set of &#8220;vcs&#8221; commands. Ultimately, we want to make it easy to grab a random open source project of the net and start hacking on it. Using the &#8220;vcs&#8221; commands, for the most common version control operations you won&#8217;t even have to think about which VCS is used by a given project.

<div align="center">
  <img style="max-width: 800px;" src="http://www.blueskyonmars.com/images/2009/08/vcs-with-svn.jpg" />
</div>

I can run &#8220;vcs clone&#8221; (&#8220;vcs checkout&#8221; also works) to check out [Bespin][4] (in a Mercurial [repository][5]), [Paver][6] (in a Subversion [repo][7]) and hopefully soon [Narwhal][8] (in a Git [repo][9]). Also new in Bespin 0.4: Bespin&#8217;s command line has been tricked out to be able to have fancier interactions with commands, so you can enter all of the extra information that Bespin needs for checking out a repository right in the output area.

If you&#8217;ve used Subversion and one of the [Distributed VCSes][10], you&#8217;ll know that they have a different model. The DVCSes do almost everything in a local repository copy and only talk to a remote server for push/pull. That&#8217;s actually true of Subversion as well, with one notable exception: commit. For Subversion, the &#8220;vcs commit&#8221; command will simply save your commit message for later. When you run &#8220;vcs push&#8221;, that is when an actual &#8220;svn commit&#8221; operation is run.

What&#8217;s neat about the &#8220;vcs&#8221; commands is that they operate the same from VCS to VCS. svn doesn&#8217;t have a feature to &#8220;add all files that are unknown&#8221;, whereas Mercurial does. &#8220;vcs add -a&#8221; operates the same on both systems.

If you&#8217;re interested, you can also use these commands on the command line by installing the [Ãœber Version Controller (uvc)][11] Python package. After doing so, you can head into a random Subversion or Mercurial working copy and type &#8220;uvc status&#8221; to see what&#8217;s different. I will note that the command line tool has been, um, lightly tested since uvc is mostly used as a library for Bespin at this point.

One final note: Bespin will soon also support native &#8220;svn&#8221; and &#8220;hg&#8221; commands so that you can stick to commands and options you&#8217;re familiar with or for performing more complex operations that don&#8217;t have equivalent &#8220;vcs&#8221; commands.

You can learn more about version control in Bespin from [this section of the User Guide][12].

<div class="zemanta-pixie">
  <img class="zemanta-pixie-img" alt="" src="http://img.zemanta.com/pixy.gif?x-id=0efb5136-be4e-8131-859c-5df0461f61fb" />
</div>

 [1]: http://labs.mozilla.com/2009/08/bespin-0-4-stop-collaborate-and-code/
 [2]: http://directwebremoting.org/blog/joe/2009/08/13/collaboration_in_bespin.html
 [3]: http://gphemsley.wordpress.com/2009/08/10/svn-support-in-bespin/
 [4]: http://labs.mozilla.com/projects/bespin/
 [5]: http://hg.mozilla.org/labs/bespin/
 [6]: http://www.blueskyonmars.com/projects/paver/
 [7]: http://paver.googlecode.com/svn/trunk/
 [8]: http://narwhaljs.org/
 [9]: http://github.com/tlrobinson/narwhal/tree/master
 [10]: http://en.wikipedia.org/wiki/Distributed_revision_control
 [11]: http://pypi.python.org/pypi/uvc/0.3
 [12]: https://wiki.mozilla.org/Labs/Bespin/UserGuide#Version_Control