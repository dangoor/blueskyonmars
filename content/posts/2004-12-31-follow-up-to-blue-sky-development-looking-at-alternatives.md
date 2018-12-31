---
title: 'Follow-up to Blue Sky Development: looking at alternatives'
author: Kevin Dangoor
type: post
date: 2004-12-31T16:13:26+00:00
url: /2004/12/31/follow-up-to-blue-sky-development-looking-at-alternatives/
categories:
  - Software Development

---
David Heinemeier Hansson wrote an excellent and thoughtful follow-up to my Blue Sky Development <a />article: Escaping Java but not its thinking</a>. This article deserves a real follow-up, which I hadn&#8217;t intended to write right now, but I did it anyhow.</p> 

I did actually take a good look at [Ruby][1]/[Rails][2], [Squeak][3]/[Seaside][4] and even [oCAML][5] and LISP/Scheme. I also looked at some commercial Smalltalk and LISPs. I even looked at [Haskell][6] to see what a better statically-typed language could look like. I didn&#8217;t talk about that in the Blue Sky Development article, though I should have. I wrote about Java (the platform) and Python primarily not because they&#8217;re languages that I know, but because they appeared to be the best options for me and I did a lot of deliberation between the two.

I&#8217;m running a small business, so I wanted to be able to take advantage of as much open source code as possible. Java and Python both had well-exercised libraries that would help my specific app. Python has some libraries that significantly exceed the Java ones in their utility for me, which is another thing that gave it the edge. I&#8217;m not going to talk specifics on this point, since my product is still in development.

In terms of language syntax, I didn&#8217;t see a large difference in the productivity I would get between using Ruby, Python, Smalltalk or the other dynamic languages.

Ruby on Rails is, hands down, the slickest integrated web framework going. Everything is right there in one package, ready to run. Zope is certainly an integrated framework, and is slick in many ways, but its model is a huge leap for many people. Zope3 simplifies the model, but introduces XML config files :(. I did consider embedding Zope3, but it&#8217;s not appropriate for my app.

Plus, it appears (to an outsider) that Rails is becoming the de facto standard web framework for Ruby. Python has no such thing, so I did have to slog through several different frameworks and choose one. The closest thing Java has to a de facto standard is [Struts][7] (no thanks!). In the end, I decided that [Quixote][8]+[SQL Object][9] provided enough framework and a pleasant working style, but they are certainly not the reason I chose Python.

Seaside looks great and it appears to be influencing people working in other languages (though I haven&#8217;t seen a Python equivalent yet). I also find Smalltalk&#8217;s notion of an image to be nifty. There&#8217;s nothing like interactively working with a system (something the pure Java folks miss out on almost entirely!)

It is worth mentioning that Python does well in the areas I cited in my article. Take performance: I don&#8217;t think Ruby has something like [Pyrex][10] which is a great bridge between C performance and your dynamic Python code. Or packaging: Ruby has [AllInOneRuby][11] and [a page describing how to build a Mac OS X app][12]. Python has [py2exe][13] and [py2app][14] which are very automated and do a good job of dependency tracking. Python also has a saved-to-disk bytecode, which is a good thing when you&#8217;re working on a closed-source app. (And, yes, I know that bytecode can be decompiled 🙂

Python also has nice modules for accessing native Windows and Mac functionality. Ruby appears to have this as well, but not all of the dynamic languages do.

In summary, my article did shortchange the effort that I put in educating myself about the alternatives. The language itself was not the biggest determining factor. While some pre-existing tools are better in other languages, Python has some tools that are better for this specific project.

 [1]: http://www.ruby-lang.org/
 [2]: http://www.rubyonrails.com
 [3]: http://www.squeak.org/
 [4]: http://www.beta4.com/seaside2/
 [5]: http://www.ocaml.org/
 [6]: http://www.haskell.org/
 [7]: http://struts.apache.org/
 [8]: http://www.mems-exchange.org/software/quixote/
 [9]: http://sqlobject.org
 [10]: http://nz.cosc.canterbury.ac.nz/~greg/python/Pyrex/
 [11]: http://www.erikveen.dds.nl/allinoneruby/
 [12]: http://rubygarden.org/ruby?BundleRubyExecutableInMacOSX
 [13]: http://starship.python.net/crew/theller/py2exe/
 [14]: http://pythonmac.org/wiki/py2app