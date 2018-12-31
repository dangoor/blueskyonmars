---
title: Changes coming to Paver
author: Kevin Dangoor
type: post
date: 2008-10-30T13:59:04+00:00
url: /2008/10/30/changes-coming-to-paver/
categories:
  - Python
tags:
  - Paver

---
[Paver][1] is the Python-based build tool that I released several months ago. It uses a Rake-like approach; you create a .py file that is filled with &#8220;tasks&#8221; which are basically just functions that can be invoked from the command line. Paver has largely been focused on automating Python projects.

Last week, I got together with Marshall and Matt from Zattoo. They&#8217;ve been working on a tool called [pytoss][2] which is focused on deployment. There are two parts to pytoss: the library and the &#8220;tool&#8221;. The library is being broken out into a new project called CloudControl, and it provides all kinds of high-level, handy deployment goodies on top of Paramiko. And it&#8217;s liberally licensed.

There&#8217;s a lot of overlap between pytoss&#8217; tool component and Paver. So, we got together to see what we can do about that. The two approaches were already quite similar. There are a handful of small differences, and I like some of the pytoss approach. At a high-level, here&#8217;s what&#8217;s going to happen:

  * the pytoss tool part will go away
  * Paver will become less Python project-specific (but won&#8217;t lose the Python project-specific features it has)
  * the small bit of magic that Paver has will go away
  * Paver will add some optional support for CloudControl for deployment
  * Paver will also inherit some nice features like the easy ability to run sub-builds (build other Paver-based projects)

These are just the changes that are in store based on the pytoss integration. There are some other cool features that I have in mind.

I have also decided to move Paver from Launchpad to Googlecode. I find Launchpad to be far more confusing, especially for a small project like Paver. Additionally, bzr&#8217;s svn plugin appears to make it so easy to sync with a central server that there&#8217;s no reason to make everyone use bzr. Those who want to, can. And those that are used to svn can use svn.

[Paver&#8217;s official homepage][1] is unchanged, there&#8217;s just a new [project page, bug tracker and source control URL][3].

A big thanks to Matt, Marshall and Jonathan for CloudControl and for helping out with Paver!

 [1]: http://www.blueskyonmars.com/projects/paver/
 [2]: http://code.google.com/p/pytoss/
 [3]: http://code.google.com/p/paver/