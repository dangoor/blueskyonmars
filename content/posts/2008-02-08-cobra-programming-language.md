---
title: Cobra programming language
author: Kevin Dangoor
type: post
date: 2008-02-08T17:18:35+00:00
url: /2008/02/08/cobra-programming-language/
categories:
  - Python

---
So, we&#8217;ve got [Jython][1] and [IronPython][2] as [Python][3] language reimplementations. There&#8217;s also [Boo][4], which is clearly heavily inspired by Python but has some interesting extensions (static typing, for example). I just came across [Cobra][5].

Cobra, like Boo, is built on the [.NET platform][6]. The syntax is clearly inspired by Python, which I consider a good thing. In keeping line noise to a minimum, Cobra even ditches the &#8220;:&#8221; at the end of the line preceding a block of code. Chuck Esterbrook has also pulled inspiration from a number of other places. I recognize some [D][7] and [Eiffel][8] in there (it&#8217;s got design by contract and unit tests built right into the classes). There&#8217;s a comparison to Python available right on the Cobra site.

Something that&#8217;s interesting about Cobra is that it&#8217;s self-hosting. Even though C# has been getting more powerful over time, I&#8217;m sure that Cobra can move forward more quickly with its even more succinct syntax.

As a Python guy, though, I can&#8217;t help but notice things that seem to be missing (or are possibly just missing from the docs).

  * Functions as first class objects. All of the examples are inside of classes, which just seems silly. I also haven&#8217;t seen the syntax for passing a function around (can you even do that?) This is a powerful feature.
  * Metaclasses don&#8217;t seem to exist in Cobra. You don&#8217;t need them all the time, but you can make some APIs a lot nicer if you use them when appropriate.
  * Function parameter declaration is weaker. Function parameter capabilities seem to be the same as in any other .NET language. It allows you to have variable arguments, but that&#8217;s about as fancy as you can get.
  * Objects are not extensible. You can&#8217;t just go and hang random attributes off of an object, and there are actually some times when this is convenient to do.

I do think it&#8217;s interesting to see more languages popping up that offer both static and dynamic typing. I&#8217;ll be curious to see how that plays out over time.

 [1]: http://jython.org/Project/index.html
 [2]: http://www.codeplex.com/Wiki/View.aspx?ProjectName=IronPython
 [3]: http://python.org/
 [4]: http://boo.codehaus.org/
 [5]: http://cobra-language.com/
 [6]: http://www.mono-project.com/Main_Page
 [7]: http://www.digitalmars.com/d/
 [8]: http://www.eiffel.com/