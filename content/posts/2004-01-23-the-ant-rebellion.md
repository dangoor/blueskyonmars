---
title: The Ant Rebellion
author: Kevin Dangoor
type: post
date: 2004-01-23T16:42:06+00:00
url: /2004/01/23/the-ant-rebellion/
categories:
  - Software Development

---
[Jon Tirsen][1], [Martin Fowler][2], and [Bruce Eckel][3] have all written recently about stumbling blocks that they&#8217;ve run into with [Ant][4]. The problem is that Ant is great when it does what you want, but if something doesn&#8217;t do what you need, there&#8217;s no full-fledged programming language to get the job done. So, Jon uses Ruby to control his build, Martin has started playing with Rake (a Ruby-based make), and Bruce is generating his Ant build files. Some other set of people use Maven to theoretically simplify their builds, but that&#8217;s not exactly the same as handling complex builds.

All of this might explain why Ant 1.6 appears to include the [Script][5] task. The Script task lets you use any BSF compatible language (of which there are many) to add more complex logic to your build. [Scriptdef][6] goes even farther, letting you create new Ant tasks in scripting languages.

Using those tools, you can take advantage of Ant&#8217;s relative ubiquity and the fact that people know how to run Ant, while being able to make your builds as complex as they need to be. I&#8217;d rather leave Ant in charge of my build process (making it easier to jack into things like Anthill) and script the complex parts.

 [1]: http://blogs.codehaus.org/people/jutopia/archives/000562_using_ruby_to_build_java_systems.html
 [2]: http://martinfowler.com/bliki/BuildLanguage.html
 [3]: http://mindview.net/WebLog/log-0046 "Bruce Eckel's MindView, Inc: 1-1-04 Why we use Ant (or: NIH)"
 [4]: http://ant.apache.org
 [5]: http://ant.apache.org/manual/OptionalTasks/script.html
 [6]: http://ant.apache.org/manual/OptionalTasks/scriptdef.html