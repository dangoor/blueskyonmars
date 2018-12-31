---
title: Blue Sky Development
author: Kevin Dangoor
type: post
date: 2004-12-29T15:09:15+00:00
excerpt: "If you had complete freedom of choice in development tools, what would you do? Here's what I did."
url: /2004/12/29/blue-sky-development/
categories:
  - Software Development

---
## Preface

My point with this article is to document my thought process in choosing a development platform. I am not out to start a language war. I&#8217;m pretty comfortable that my facts are correct, and I _know_ that my opinions are correct, because they are just opinions and they are mine. You may choose to disagree with my opinions, if you wish. If you do find a factual error in here, please do add a comment to the posting.

## Introduction

Ahh,&#8230; wide-open, blue sky development, with no legacy to hold you down. Legacy code can be handy because it incorporates a lot of [useful knowledge][1] about your problem domain, even if the way it&#8217;s implemented makes you cringe. On the other hand, when you&#8217;re entering a whole new area, you get complete freedom to explore and to use the best current tools and practices.

What could be better than doing fresh development with no legacy? Having no legacy and being the boss, of course! Technology choices can be made on technical (and business) merit without politics getting in the way. If given a complete choice of tools platforms, would developers truly go for Java or .NET (or &#8220;legacy&#8221; Microsoft APIs) or would they [choose LISP or Python or OCAML][2]?

I would imagine that developers would be all over the map in terms of their ideal choices. Some would certainly pick one of the dominant platforms. Choosing Java for a project is not unreasonable, for a programmer that&#8217;s familiar with it. Java is reasonably high-level (most importantly, you don&#8217;t have to manage your own memory) and has lots of good open source libraries.

## Some background

I&#8217;ve been largely working in Java for the past four years. There&#8217;s also been plenty of Perl mixed in there, and even a little PHP. Having worked in several languages, choosing Java straight away is not a slam dunk. Here are the characteristics of my app:

  * Has a component that runs on desktops (consumer/individual business user)
  * Likely maintaining a database in the tens of megabytes
  * Has a web-based component
  * Needs to support some level of plugins/scriping
  * Needs to be cross-platform (I use both Macs and PCs)
  * The app is not free.

Running on the desktop means that the application should not be too resource hungry, and the download size should be kept reasonable. I don&#8217;t think everyone has a JVM installed. It may not be too onerous to require people to install one, but that&#8217;s one more headache. People are a lot less inclined to buy something if they need to jump through hurdles. I can probably get away with static compilation with gcj so that people don&#8217;t need a JRE. It&#8217;s nice to have that option.

## Lots to choose from

Embeddable databases are available for Java (Derby, Axion, HSQL, plus a number of non-SQL databases). Embedding a webserver with Java is easy. Supporting scripting and plugins is easy, with the many good choices. Java is certainly cross-platform.

So, Java meets all of the criteria required for the app. So does Perl. So does Python. So does Ruby. Heck, so does Squeak Smalltalk. CompSci is all about tradeoffs, so I need to look at the tradeoffs between these choices.

I love Perl for quick, one-off scripts. I hate it for anything else. Perl is _very_ easy to write, because there are so many ways to accomplish something. Just use the first that comes to mind. Perl is a pain to _read_ because of that same reason. Your mind actually has more work to do to figure out what that piece of code you wrote three months ago does. And, if you didn&#8217;t write that code, it takes even more thought.

Ruby looks nice and [Rails][3] is attracting a lot of attention for good reason. [Seaside][4] on Squeak _should_ be attracting attention, because it looks like a very productive way to put together apps. There are two problems with both of these: 1) I don&#8217;t know them, and 2) they are less mature and have smaller communities than Python or Java. I can certainly overcome (1), but that would slow me down initially. The clock is ticking, because I need to generate money to pay my mortgage and all that&#8230; The second point also means slower velocity: there are fewer places to turn for help. There are fewer prepackaged modules, and those modules may be less-tested.

That brings me to Python. I&#8217;ve used Python on and off since &#8217;95, so I have a comfortable familiarity with it. My last go at self-employment was based on work in Python. That was five years ago, though, so there are some new things I need to pick up. I think there are some [Java-isms to unlearn][5] as well. But, the ramp-up time with Python would not be as great as with a language that I haven&#8217;t worked in.

## Java-the-language

A bit of opinion: Java sucks. Not Java-the-platform, but Java-the-language. First of all, there&#8217;s the whole [static vs. dynamic][6] typing argument. Going beyond that, though&#8230; static typing in Java [is not as safe as it could be][7]. Until Java 5, Collections were dynamically typed constructs (with the annoying extra typing of doing a cast). Autoboxing in Java 5 is a nice convenience feature to avoid manual casting and conversion, but it leaves some ambiguity about what happens if you have a null value.

Java is practically unusable without an IDE, because Java&#8217;s implementation of static typing requires a lot of keyboard typing on the part of the programmer. It doesn&#8217;t have to be that way. Some statically typed languages use [type inference][8], because the compiler can often figure out exactly what you mean without requiring you to type it in. Here&#8217;s an example:

> String foo = bar.toString();

The compiler _knows_ that bar.toString() returns a String, and yet you still have to type String at the beginning of the line.

Java doesn&#8217;t support operator overloading. Many people call this a good thing, largely because operator overloading can be and certainly has been abused. But, because of this, using a Map requires mapName.get(key) and mapName.put(key, value), rather than the more natural mapName[key] and mapName[key] = value.

Java doesn&#8217;t have first-class functions and reflection can be somewhat painful to use. You&#8217;re forced to create an interface for every kind of operation that you might want to be able to perform (for example, Comparator). If you use reflection, you have to deal with the painful syntax _and_ you lose your static typing.

Java doesn&#8217;t have any kind of multiple inheritance, so mixing in behavior requires using AOP, static utility methods, or using composition and delegation. I do understand how multiple inheritance complicates things, but Java doesn&#8217;t provide any convenient mechanism for sharing behavior. Java 5 static imports do provide one mechanism to help here, which is a good start.

Making the distinction between Java-the-language and Java-the-platform is an important distinction. The [Nice language][9] fixes all of these Java language problems with the exception of operator overloading. [Groovy][10] even includes operator overloading and the ability to be dynamically typed. I&#8217;ll come back to these two choices.

## What about performance

Java is fast. That&#8217;s the bonus you get from static typing&#8230; many operations can just become a quick lookup or jump to a memory location. In Python, every name lookup essentially requires a hash lookup. While this is an O(1) operation, it&#8217;s still going to be slower than memory referencing.

I can&#8217;t find the reference now, but I recently saw someone write that making a language choice based upon performance is the ultimate premature optimization. As long as there are ways to get acceptable performance, the language should be chosen based upon the expected level of productivity.

So, what about Python&#8217;s performance? Many people have called it &#8220;slow&#8221;. I don&#8217;t think Python is slow. Sure, it&#8217;s _slower_ than Java. But, it&#8217;s fast enough on even late-&#8217;90s hardware to do many tasks at a speed that is comfortable to users. Depending on your specific needs, [Ian Bicking offers some tips][11] for improving your performance without leaving Python.

Let&#8217;s assume that Python is _still_ too slow for something you&#8217;re trying to do. If you&#8217;re using an x86 machine, you can use Psyco</em> to speed up parts of your code with a trivial amount of work. I&#8217;m not only targeting x86, though. For me, there&#8217;s [Pyrex][12], which looks kinda like Python, but compiles into C extension modules.</p> 

Finally, it&#8217;s worth pointing out that a lot of heavy lifting in Python is done in C code (and much of that C code is tried-and-true, having been around for a long time). Python itself is written in C, so things like hashtable lookup are as fast as they&#8217;re likely to get. If you want to add something like encryption to your app, that would most likely be done by adding a C extension module. This helps contribute to the notion that putting together an app in Python is likely to be fast enough. In fact, Python is popular in scientific circles because it&#8217;s easy to write code in and experiment, while the parts that need to be fast are written in C and are plenty fast.

The JVM is fast. Dynamic languages, like Groovy, incur the same kind of overhead that Python does, since name resolution needs to be done at runtime. One nice thing about JVM languages is that if you need more performance, you just switch that bit of code over to Java. That would certainly seem easier than moving that bit of code into C. (Pyrex mitigates this a bit, though.)

The JVM has been shown to be almost as fast as C, but not quite. So, a dynamic language on the JVM will likely be a little slower than a dynamic language implemented in C. Similarly, optimized modules in C will likely be faster than those written in Java. Despite the fact that Python is, without question, slower than Java, I think there are enough optimization options that most apps can reach the performance level needed.

## Packaging Options

Sun really wants people to have a JVM installed (just as Microsoft wants everyone to have the .NET Runtime). Maybe there are enough people with the JVM installed now that it really isn&#8217;t an issue.

Sun has improved desktop integration considerably, which is important for making usable, consumer-oriented products. Kudos on that count.

Though Sun may not like it, the Azureus folks have shown how good Java packaging can be. They used [GCJ][13] and [SWT][14] to create a solid app that feels like it belongs on the Mac or PC that you&#8217;re using.

Python has great desktop integration (you can call Windows and Mac APIs directly, and [wxPython][15] provides cross-platform GUIs). Extra nice, though, is that people have put together [py2exe][16] and [py2app][17] that create standalone Windows and Mac apps, respectively. Since the Python interpreter is bundled right into the executable, you don&#8217;t lose any of Python&#8217;s dynamic nature.

## Final thoughts

I&#8217;m sure it&#8217;s clear by now that I chose Python to implement my project. Of key importance is productivity, and I think that dynamic languages win in that regard. Though I&#8217;m using Python, there are plenty of good languages to choose from. Even if you&#8217;re targeting the Java platform, I&#8217;d recommend checking out the dynamic languages that are available. Some of them are more mature than you might expect and, since they&#8217;re written in Java, it&#8217;s usually quite easy to figure out how they work and decide if you like the implementation.

Every project has its own requirements. If you&#8217;re lucky, you&#8217;ll be free to choose the right tools for the job.

 [1]: http://www.joelonsoftware.com/articles/fog0000000069.html
 [2]: http://www.paulgraham.com/gh.html
 [3]: http://www.rubyonrails.com
 [4]: http://www.beta4.com/seaside2/
 [5]: http://dirtsimple.org/2004/12/python-is-not-java.html
 [6]: http://www.mindview.net/WebLog/log-0025
 [7]: http://nice.sourceforge.net/safety.html
 [8]: http://c2.com/cgi/wiki?TypeInference
 [9]: http://nice.sourceforge.net/language.html
 [10]: http://groovy.codehaus.org/
 [11]: http://dirtsimple.org/2004/12/perception-of-speed.html#c110270144133808384
 [12]: http://nz.cosc.canterbury.ac.nz/~greg/python/Pyrex/
 [13]: http://gcc.gnu.org/java/
 [14]: http://www.eclipse.org/articles/Article-SWT-Design-1/SWT-Design-1.html
 [15]: http://www.wxpython.org/
 [16]: http://starship.python.net/crew/theller/py2exe/
 [17]: http://pythonmac.org/wiki/py2app