---
title: Paver and the building, distribution, deployment etc. of Python projects
author: Kevin Dangoor
type: post
date: 2008-04-22T16:45:48+00:00
url: /2008/04/22/paver-and-the-building-distribution-deployment-etc-of-python-projects/
categories:
  - Python
tags:
  - Paver

---
This morning, I released a new open source &#8220;build tool&#8221; aimed at Python projects: Paver. The goal of Paver is to provide a smooth way to script up the management of your Python projects. You can read all about it on the [Paver site][1], but I wanted to provide some background here.

## Look at all these tools!

Python programmers have a great many tools at our disposal. We have tons of libraries that make it so that we don&#8217;t have to write lots of code to get our software built. We also have a broad collection of tools to help us manage our projects.

  * Python&#8217;s standard library includes [distutils][2], for packaging up and distributing Python projects.
  * [setuptools][3] is almost part of the standard library, and quite a few projects require it. setuptools gives you cross-platform dependency management, more packaging options, script generation and a simple plugin framework.
  * [zc.buildout][4] helps you with the creation of repeatable, easily installed ready-to-run installations of projects. It gives you a contained environment so that you don&#8217;t need to muck with the global Python configuration on the system to make a working installation.
  * zc.buildout supports [&#8220;recipes&#8221;][5] that handle installation and configuration of various parts that your Python project may need
  * [virtualenv][6] gives you just the contained installation part of zc.buildout, but it does it in a slightly different way that I&#8217;ve found easier for certain, not-egg-friendly projects.
  * [PasteScript][7] can be used to generate configuration files and complete skeleton projects
  * [Sphinx][8] is a new package for generating documentation from ReStructred Text sources. It&#8217;s very cool, and it&#8217;s what I used for Paver&#8217;s site.
  * and there are many, many more

## Seems great, what&#8217;s the problem?

I have personally used all of these tools at one time or another. In fact, I&#8217;ve used them all recently. In working with them, I couldn&#8217;t help but notice some aspects that made my life harder than it needed be.

For example, when using distutils or setuptools, it&#8217;s very easy to add behavior that runs before or after the setup command, because your setup files are just plain Python. It&#8217;s not as easy to customize the way a command behaves, or to add a new command entirely. You need to read the docs, make a new class and register that class somehow.

zc.buildout is awesome and makes it easy to get a predictable collection of components installed. It uses an INI file as its file format, which means that adding behavior is not straightforward. Creating a new zc.buildout recipe is very much like creating a new setuptools command: create a separate class and refer to it an in egg. I believe there&#8217;s a zc.buildout recipe for putting some commands in your INI file. Do you want Python code in your INI file?

Which also brings up another point: distutils and setuptools use a Python file and keyword parameters for their configuration. (There is also an optional INI file.) zc.buildout uses an INI file. Sphinx uses a .py file.

## What would I want?

It seemed to me that life would be better if:

  * If I need to do something that takes 5 lines of Python, I could do it in little more than 5 lines of Python without adding another file for that purpose.
  * If configuration could take on a consistent, predictable form
  * If things that I do often in managing my projects took even less Python to script.
  * If the system could be used easily with multiple projects by not requiring anything else, but taking advantage of other packages when they&#8217;re present

It is with those goals and looking around that Paver came into existence. As with TurboGears, I did not want to reinvent the various parts of the whole that I&#8217;m angling for. The idea is to use zc.buildout&#8217;s machinery, not reinvent it. I used Jason Orendorff&#8217;s great path.py module rather than inventing my own abstraction there.

I didn&#8217;t set out to invent the scripting format, either. I seriously considered Zed Shaw&#8217;s [Vellum][9] which has shaped up quite nicely. But in trying it out, I realized that I really wanted my projects managed by Python scripts that had little headache and little overhead. Doing computations, loops and breaking code up into separate functions (or other organizing blocks) are all obvious for a Python programmer if the language is Python. For the record, Zed wants his build files to be just &#8220;data&#8221;, for perfectly rational reasons. For me, though, I want Python.

Now for the &#8220;this is an **early release caveat**&#8220;. Paver is functional, and I use it. But, its support for the various libraries is quite shallow right now, and zc.buildout/virtualenv are not at all represented yet. What I&#8217;ve released is basically the parts that I&#8217;ve needed so far, and I&#8217;ll be adding on as I need things. I figured that if others think the approach is worthwhile, we can pool our efforts and build out the [Paver Standard Library][10] a bit quicker. I should also note that while Paver should work on Windows, it&#8217;s only been used on Macs and Linux. Finally, it&#8217;s possible that Paver&#8217;s pavement.py syntax may change along the way to 1.0, but I can promise to document those changes and I don&#8217;t expect a great deal of pain in making the transitions.

Note also that if you maintain a Python library that is useful in helping people work with the projects, it&#8217;s easy to add Paver targets and such to your own library. Paver itself includes support for other libraries because of the chicken-and-egg problem. People won&#8217;t support Paver until people are using it and people wouldn&#8217;t use it if it didn&#8217;t support the kinds of things that people already do. So, Paver includes the connectors for the libraries that I need.

I&#8217;ve set up all of the various project goodies for Paver:

  * [Website][11]
  * [Launchpad project][12]
  * Public bzr branch:
    
    <span style="font-family: Times; font-size: 16px;"><span style="font-family: -webkit-monospace; font-size: 12px; line-height: 20px;"><span class="pre">bzr</span> <span class="pre">branch</span> ht<span class="pre">tp://bazaar.launchpad.net/~dangoor/paver/main</span></span></span>
  * <span style="font-family: -webkit-monospace; line-height: 20px;"><a href="http://groups.google.com/group/paver">Mailing list</a></span>

Ian Bicking has given me a great mass of useful feedback, which I have not yet fully digested. Mark Ramm, Ben Bangert and David Stanek also had some helpful input.

And, I&#8217;d love to hear more from <span style="font-style: italic;">you</span>!

 [1]: http://www.blueskyonmars.com/projects/paver/
 [2]: http://docs.python.org/lib/module-distutils.html
 [3]: http://peak.telecommunity.com/DevCenter/setuptools
 [4]: http://pypi.python.org/pypi/zc.buildout
 [5]: http://pypi.python.org/pypi?%3Aaction=search&term=buildout+recipe&submit=search
 [6]: http://pypi.python.org/pypi/virtualenv
 [7]: http://pythonpaste.org/script/
 [8]: http://sphinx.pocoo.org/
 [9]: http://www.zedshaw.com/projects/vellum/
 [10]: http://www.blueskyonmars.com/projects/paver/paverstdlib.html
 [11]: http://www.blueskyonmars.com/projects/paver/index.html
 [12]: https://launchpad.net/paver/