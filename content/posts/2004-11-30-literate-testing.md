---
title: Literate testing
author: Kevin Dangoor
type: post
date: 2004-11-30T20:41:42+00:00
url: /2004/11/30/literate-testing/
categories:
  - Software Development

---
The notion of Literate Programming has been around for a while, but I&#8217;ve never seen it used in real life. The concept is very simple: put your code and documentation in the same file. &#8220;Documentation&#8221; in this sense, is not comments, but something more akin to Javadoc. When you comment your code, you&#8217;re basically adding comments to a source code file. In literate programming, you add your code to a document file. One example of a literate programming tool that I&#8217;m aware of is [LEO][1] .

Proponents of unit tests, including me, say that the unit tests provide good documentation for a class. They tell you how to use the class, and come with a built-in guarantee that it runs as advertised (assuming you run your tests regularly). This can be effective, if the unit tests are easy to find (like in a file right next to the class).

Philip Eby wrote [an article about his eureka! moment][2] with the Python doctest module. Intriguingly, what Philip writes about could be described as &#8220;Literate Testing&#8221;. Since unit tests already help perform a documentation function, actually building up a more descriptive document around your tests seems like a good idea. It&#8217;s a way to describe some of the rationale behind the code, instead of just describing how you use it. It also provides a chance to describe (possibly including more tests) how the class fits into the big picture of the overall system.

Any text documentation can certainly get out of date, whether it&#8217;s javadoc or docs that flow along with the tests. I like the idea of putting the docs with the tests, rather than with the code, because the part of the development where you&#8217;re writing the test is where you&#8217;re thinking at a higher-level about what you&#8217;re going to do. When you get into the code, you&#8217;re down to thinking about how you&#8217;re going to implement the feature. Javadoc is not quite ideal for this, but [agiledox][3] (testdox) could be pushed in this direction.

Python&#8217;s [doctest][4] module lets you put the tests right into a documentation string that appears either in your main source file or in a separate test file. Philip likes the idea of putting the docs and tests in a file separate from the code, and I do, too. I think it makes the flow of reading the docs/tests and the flow of reading the code a lot more pleasant.

The recent disgruntled rumblings in the Java community about JUnit and its lack of evolution have led people to think of alternatives, like [TestNG][5]. One interesting alternative to consider is doctest. Since Jython can import Java classes, there&#8217;s no reason that you couldn&#8217;t interactively test a Java class and write a file containing doctest-compatible tests that exercise your Java classes.

 [1]: http://webpages.charter.net/edreamleo/front.html
 [2]: http://dirtsimple.org/2004/11/stream-of-consciousness-testing.html
 [3]: http://joe.truemesh.com/blog/archives/agile/000047.html
 [4]: http://www.python.org/doc/current/lib/module-doctest.html
 [5]: http://www.beust.com/testng/