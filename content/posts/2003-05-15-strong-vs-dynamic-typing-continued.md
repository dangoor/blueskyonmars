---
title: Strong vs. Dynamic Typing Continued
author: Kevin Dangoor
type: post
date: 2003-05-15T18:58:13+00:00
url: /2003/05/15/strong-vs-dynamic-typing-continued/
categories:
  - Technology

---
In the continuing discussion on [Dave Copeland&#8217;s site][1], Dave asked what is limiting about a strongly typed language like Java. This is a very good question, and I&#8217;ve given it a little thought.

Clearly, anything that can be done in Python, Ruby, etc. can also be done in Java. It&#8217;s just a question of how much pain is involved. There are some decent points in [this discussion on Artima:][2]

> &#8211; &#8220;Duck Typing&#8221;: See http://c2.com/cgi/wiki?DuckTyping. One of the frustrations of static typing is to have two classes from two different sources that have similar interfaces but inherit from no common types. For example, Java 1.4 added a CharSequence interface; before that, the only way to write a library that operated on Strings, StringBuffers, and char arrays was either to pass them as Object (as the GNU regex library does), overload and reimplement methods for all known types (as I think ORO does), or to create an adaptor (as Apache Regex does). On the other hand, a Python or Ruby object doesn&#8217;t have to inherit from X; it merely has to implement enough of X&#8217;s methods (ideally all) in order to be X-like enough to be sustitutable, in the Liskov sense.
> 
> &#8211; Ease of Refactoring: Because of Duck Typing, changing the type of an argument or a return value from a simple type to a more complex one is a lot easier in a dynamically-typed language. In a statically-typed language, you have to change all code that uses that type, if it and the old type don&#8217;t share an interface, or if the usage declared the concrete type. You&#8217;d also have to change the type of any variable or collection that held the argument or return value without using it directly. 

I do agree with these things, but when I strip the argument down to the essentials, I think I&#8217;m willing to concede Dave&#8217;s point. Just about any realistic problem can be managed with interfaces or, at worst, using a design pattern like Decorator. And the &#8220;Ease of Refactoring&#8221; point is somewhat negated by good refactoring tools like the ones in Eclipse.

So, why are all of these people speaking out in favor of dynamically typed language? For exactly the reason the Dave talks about: Python, Perl, Ruby, etc. all have a large number of language features that are orthogonal to strong typing that make them far more productive.

As an aside: one example that a lot of dynamic typing proponents seem to bring up is the Iterators/Collections mess in Java. Thank goodness that Java 1.5 generics will fix that. But, that&#8217;s just one small piece of making Java a more productive language.

 [1]: http://www.naildrivin5.com/davec/archives/000041.shtml
 [2]: http://www.artima.com/forums/flat.jsp?forum=32&thread=3572 "News & Ideas Forum - Strong versus Weak Typing"