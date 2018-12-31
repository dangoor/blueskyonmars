---
title: Configuration management for non-Java apps
author: Kevin Dangoor
type: post
date: 2005-07-15T18:40:57+00:00
url: /2005/07/15/configuration-management-for-non-java-apps/
keywords:
  - python,programming,rails
categories:
  - Software Development

---
Patrick Peak seemed to have misinterpreted [no deployment means for a Rails app][1]. I&#8217;m certain that we&#8217;re talking about &#8220;no deployment&#8221; during development. Compared to \*some\* Java environments, it is a big win to be able to just try something and refresh the page. However, especially for folks doing test-driven development, I think this is definitely not the biggest win from Rails.

In Java, it is pretty well standardized that folks bundle up a war file, which they then toss onto their production app server at the right time. Patrick points out that you can change JSPs and even .java files on some app servers, if you wish. But, people certainly don&#8217;t do that on production servers.

And the same is true of anyone who&#8217;s been doing software for a while, regardless of language. You only need to be bitten once to learn that having a solid production deployment plan and tools is critical.

James Duncan Davidson describes exactly how he deploys Rails apps: [Rails: Sandbox, Develop, and Deploy][2]. For anyone who hasn&#8217;t been bitten by a bad change on a production server, I&#8217;d recommend reading that. He describes a very solid way of going from rapid development to trouble-free deployment.

From Patrick&#8217;s article, regarding deployment of a Rails app:

> Developers deploy to a testing or production by manually zipping up the project and copying to the server. (Since there is no Ant to do it for you). Anything I&#8217;m missing here?

The answer is &#8220;yes&#8221;. What Patrick is missing is that Perl, Python and Ruby are all excellent &#8220;scripting languages&#8221; (some are more excellent than others, but I won&#8217;t go there&#8230;) I know firsthand that moving files around to get just the right subset and zipping up those files is a nice, short script in Python thanks to modules like shutil and zipfile.

My process for Zesty News is similar to what James talks about in his article. Getting a new machine up and running to do development on Zesty News is easy:

1. Install Subversion
  
2. Check out the project
  
3. Install a few pre-reqs (Python 2.4.1 primarily. On Windows, there are a couple other things needed to get a sane build environment. That will go away before too long, though.) All of the pre-reqs are right there in the project.
  
4. In the top directory of the project, python build.py modules. This builds additional components used by Zesty News.
  
5. At this point, the unit tests and the app are ready to run.

To create an executable, I just run &#8220;python build.py app&#8221;.

There are all kinds of things that need to happen to pull all of the pieces together. There&#8217;s no way I would do that stuff by hand. My &#8220;build.py&#8221; script and the various commands for it are one of the first things that I did. It&#8217;s not a lot of code, and I really don&#8217;t miss ant.

Just using agile languages does not imply a lack of good configuration management.

 [1]: http://www.patrickpeak.com/comments/patrick/Weblog/rails_where_are_the_implications
 [2]: http://blog.x180.net/2005/07/rails_sandbox_d.html