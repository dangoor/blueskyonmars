---
title: Paver 1.0 released!
author: Kevin Dangoor
type: post
date: 2009-03-23T13:10:23+00:00
url: /2009/03/23/paver-10-released/
categories:
  - Paver
  - Python

---
At long last, I&#8217;ve released [Paver][1] 1.0. Here&#8217;s the announcement that I sent to python-announce:

After months of use in production and about two months of public testing for 1.0, Paver 1.0 has been released. The changes between Paver 0.8.1, the most recent stable release, and 1.0 are quite significant. Paver 1.0 is easier, cleaner, less magical and just better all around. The backwards compatibility breaks should be easy enough to work around, are described in DeprecationWarnings and were introduced in 1.0a1 back in January.

Paver&#8217;s home page: http://www.blueskyonmars.com/projects/paver/

### What is Paver?

Paver is a Python-based software project scripting tool along the lines of Make or Rake. It is not designed to handle the dependency tracking requirements of, for example, a C program. It \*is\* designed to help out with all of your other repetitive tasks (run documentation
  
generators, moving files about, downloading things), all with the convenience of Python&#8217;s syntax and massive library of code.

If you&#8217;re developing applications in Python, you get even more&#8230; Most public Python projects use distutils or setuptools to create source tarballs for distribution. (Private projects can take advantage of this, too!) Have you ever wanted to generate the docs before building the source distribution? With Paver, you can, trivially. Here&#8217;s a complete pavement.py::

<pre lang="python">from paver.easy import *
    from paver.setuputils import setup
    
    setup(
        name="MyCoolProject",
        packages=['mycool'],
        version="1.0",
        url="http://www.blueskyonmars.com/",
        author="Kevin Dangoor",
        author_email="dangoor@gmail.com"
    )
    
    @task
    @needs(['html', "distutils.command.sdist"])
    def sdist():
        """Generate docs and source distribution."""
        pass
</pre>

With that pavement file, you can just run &#8220;paver sdist&#8220;, and your docs will be rebuilt automatically before creating the source distribution. It&#8217;s also easy to move the generated docs into some other directory (and, of course, you can tell Paver where your docs are stored, if they&#8217;re not in the default location.)

### Installation

The easiest way to get Paver is if you have setuptools_ installed.

<pre>easy_install Paver</pre>

Without setuptools, it&#8217;s still pretty easy. Download the Paver .tgz file from [Paver&#8217;s Cheeseshop page][2], untar it and run:

<pre>python setup.py install</pre>

### Help and Development

You can get help from the [mailing list][3].

If you&#8217;d like to help out with Paver, you can check the code out from Googlecode:

<pre>svn checkout http://paver.googlecode.com/svn/trunk/ paver-read-only</pre>

You can also take a look at [Paver&#8217;s project page on Googlecode][4].

 [1]: http://www.blueskyonmars.com/projects/paver/
 [2]: http://pypi.python.org/pypi/Paver/
 [3]: http://groups.google.com/group/paver
 [4]: http://code.google.com/p/paver/