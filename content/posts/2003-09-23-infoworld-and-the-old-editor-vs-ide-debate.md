---
title: InfoWorld and the old editor vs. IDE debate
author: Kevin Dangoor
type: post
date: 2003-09-23T15:47:58+00:00
url: /2003/09/23/infoworld-and-the-old-editor-vs-ide-debate/
categories:
  - Software Development

---
Maggie Biggs writes in [InfoWorld: Code editors renew approach to IDEs][1] that many people are finding that they are more productive with standalone editors (vim, Emacs) than IDEs. Of course, Emacs with all of the Java tools incorporated could readily be considered an IDE.

My opinion is that using a &#8220;standard&#8221; text editor in conjunction with ant is less productive than an IDE (again, including tricked out Emacs in the IDE camp). Particularly in a statically-typed, verbose language like Java, having code completion and useful inter-class navigation features is a huge win. Having an integrated JUnit view (red bar/green bar) makes test driven development very zippy.

From the article:

> Some IDEs are taking this to heart; more open IDEs, such as Eclipse, are beginning to implement a flexible development approach by offering one or more editors and pluggable modules within the IDE.

&#8220;Beginning to&#8221;? Eclipse is built from the ground up as a flexible tools platform, and I would venture to say that it&#8217;s every bit as flexible as Emacs. Only it&#8217;s written in Java, so extending Eclipse is probably a bit more accessible to many of its users. Starting with 3.0, there will be an increase in the number of standalone apps built on top of Eclipse, and that will show just how flexible it is.

One positive note about the article: it ends with a recommendation to give developers some control over the development tools they use. I definitely agree with this. There is value, particularly in XP shops, in using the same tools&#8230; but just as important as standardization is the need to experiment and try new things out.

 [1]: http://www.infoworld.com/article/03/09/19/37FEcodeedit_2.html "InfoWorld: Code editors renew approach to IDEs: September 19, 2003: By Maggie Biggs: Application Development"