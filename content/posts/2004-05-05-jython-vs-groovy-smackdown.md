---
title: Jython vs. Groovy smackdown
author: Kevin Dangoor
type: post
date: 2004-05-05T19:52:35+00:00
url: /2004/05/05/jython-vs-groovy-smackdown/
categories:
  - Software Development

---
OK, sorry for the headline. Tim Bray recently [wrote a bit about Jython][1]. I agree wholeheartedly about the use of dynamic scripting languages with Java. I also agree that Jython is a very fine product and love the Python language.

But, when looking to do scripting on top of Java, I think Groovy is going to be a great choice. The big trouble with scripting your Java apps in Jython is that you need to make the mental shift over to Python syntax. With Groovy, most legal Java syntax works just fine. So, if the Java-ism for doing something is what comes to mind quickly, you can write it that way. The times when you&#8217;re trying to really save on some work, you do things in a more Groovy way.

Jython does have the maturity advantage, as Tim points out. The ability to use premade libraries written in Python _or_ Java is a bonus&#8230; just remember, though, that Python libraries tend to be rather, well, Pythonic. This is a good thing, if you&#8217;re a python geek like me, but might make things a little less intuitive for people who are used to doing things the Java way.

I&#8217;ve been following the discussions on the groovy-user mailing list (and will probably join the JCP list), and I think there&#8217;s a good direction there. People are conscious of the tradeoffs between being Java-like, and building conveniences into the language.

Groovy works quite well already. If you haven&#8217;t tried it, give it a whirl. Once the Eclipse plugin works in new Eclipse builds and has the spiffy testrunner that I&#8217;m used to, I plan to start using Groovy for unit tests. I&#8217;ve already found a good minor role for it in the app we&#8217;re building as well. So, though I&#8217;m a Python fan, I think Groovy is the finer scripting choice for Java.

 [1]: http://www.tbray.org/ongoing/When/200x/2004/05/03/Pedroni "ongoing · Jython"