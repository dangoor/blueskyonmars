---
title: Paver 1.0b1 released
author: Kevin Dangoor
type: post
date: 2009-03-13T13:15:47+00:00
url: /2009/03/13/paver-10b1-released/
categories:
  - Paver
  - Python

---
I&#8217;ve just released Paver 1.0b1. This new release adds a fun little feature. A typical setup.py script looks like this:

<pre lang="python">from distutils.core import setup

setup(name="Foo", ...)
</pre>

With the new version of Paver, you can now rename setup.py to pavement.py (or run `paver -f setup.py`) and then do:

<pre lang="python">from paver.setuputils import setup

setup(name="Foo", ...)</pre>

That gets you going quite quickly, doesn&#8217;t it? Of course, you&#8217;d likely want to add `from paver.easy import *` and to start making tasks that take advantage of Paver.

1.0b1 includes some other bug fixes, brings back the call_task function (particularly useful for distutils tasks), and makes the help output more consistent.

There&#8217;s one more bug on my list to fix (the distutils output is not showing up), and then I need to rework the docs for Paver 1.0.

**Update:** It occurred to me a bit later that my example above doesn&#8217;t work, because you need to call install\_distutils\_tasks to get Paver to pick up all of the distutils/setuptools commands. However, this will be fixed in rc1.