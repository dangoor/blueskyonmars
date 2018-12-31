---
title: 'Pack ant task: smallest set of classes needed to run'
author: Kevin Dangoor
type: post
date: 2004-01-29T22:31:54+00:00
url: /2004/01/29/pack-ant-task-smallest-set-of-classes-needed-to-run/
categories:
  - Software Development

---
Joel raised maybe slightly less hubbub than usual with his latest article [Please Sir May I Have A Linker?][1]. In there, he rants about the giant size of the .NET runtime and his desire to just include the classes he needs. Though this doesn&#8217;t eliminate the need for the Java runtime, <a title="The <pack> Ant Task&#8221; href=&#8221;http://sadun-util.sourceforge.net/pack.html&#8221;>The <pack> Ant Task</a> _does_ give you one jar file with everything you need (and no more!). (*) Assuming it works as advertised&#8230; I haven&#8217;t tried it yet.

 [1]: http://www.joelonsoftware.com/articles/PleaseLinker.html