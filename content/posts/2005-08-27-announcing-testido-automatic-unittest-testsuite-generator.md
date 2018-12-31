---
title: Announcing Testido automatic unittest TestSuite generator
author: Kevin Dangoor
type: post
date: 2005-08-27T14:47:16+00:00
url: /2005/08/27/announcing-testido-automatic-unittest-testsuite-generator/
keywords:
  - testing,unittest,programming
categories:
  - Python

---
For a project I&#8217;m working on, I didn&#8217;t want to introduce a dependency on py.test. I also didn&#8217;t want to manually write test suites myself. So, here&#8217;s [Testido][1]: a simple unittest extension that easily hooks in to however you&#8217;re testing now and eliminates the need to manually write suites.

Through the wonder of [setuptools][2], Testido can be installed trivially with easy_install.

The simplest usage looks like this:

<pre>from setuptools import setup
setup(name='foo',
      version='1.0',
      packages=['foo'],
      )
</pre>

Running &#8220;python setup.py testido&#8221; with that setup file will run all of the tests it can find in the &#8220;foo&#8221; package. Doesn&#8217;t get much easier than that, does it?

Alternatively, you can create a TestSuite that can be used by other tools like this:

<pre>from testido import collector
suite = collector.Collector("foo")
</pre>

As I point out in the docs, Testido is not a full substitute for [py.test][3] or [Testoob][4]. 

But, if you are using the stdlib&#8217;s unittest for whatever reason, it can make your life easier.

 [1]: http://www.blazingthings.com/dev/testido/
 [2]: http://peak.telecommunity.com/DevCenter/setuptools
 [3]: http://codespeak.net/py/current/doc/test.html
 [4]: http://testoob.sourceforge.net/