---
title: 'Python packaging/install: what I want'
author: Kevin Dangoor
type: post
date: 2009-08-28T18:48:51+00:00
url: /2009/08/28/python-packaginginstall-what-i-want/
categories:
  - Python
tags:
  - buildout
  - deployment
  - distutils
  - packaging
  - pip
  - setuptools
  - virtualenv

---
Python packaging and deployment can be annoying. It&#8217;s been nearly 4 years since I released the first TurboGears release as an early adopter of setuptools/easy_install. Since then, there&#8217;s been the release of [virtualenv][1], [pip][2] and [zc.buildout][3]. Somehow, it still seems like more trouble than it should be to get development and production environments set up.

On Bespin, I&#8217;ve been using a combination of virtualenv and pip (scripted with [Paver][4]) in development and production environments. But, I&#8217;ve found [pip &#8211;freeze to be nearly unusable][5].

## My Ideal World

After monkeying with this stuff a fair bit over the past few years, I have an idea of what I&#8217;d really like to have but I don&#8217;t think anyone&#8217;s working on it. I&#8217;d love to hear contrasting opinions or learn about projects that I&#8217;m not aware of.

  * Multiple version installation into global site-packages, as easy_install currently works (put the active package in the .pth file)
  * The better error reporting of pip (pip doesn&#8217;t meet my first desire, though, because it installs as single-version-externally-managed)
  * A tool to manage the installed packages (uninstall, select a different version)
  * In addition to a global site-packages, it would be nice to be able to specify a different site-dir for machines where I don&#8217;t have or don&#8217;t want to use root access
  * virtualenv that behaves like &#8211;no-site-packages but knows where site-packages (or the other site-dir) is
  * That tool that manages installed packages can selectively install specific versions of packages into the virtualenv by adding pointers in the .pth file that point to the site-packages directory
  * You can also install only into the virtualenv if you wish.
  * Install packages in that manner from a list of requirements (as with pip&#8217;s requirements file)
  * A way to freeze the currently set installed into the virtualenv as a new requirements file
  * An optional cache of all of the original sdists of the installed packages

pip is close to being usable, except freeze doesn&#8217;t work. zc.buildout is close to being usable, too. I think there&#8217;s a [&#8220;freeze&#8221; like plugin][6] for it, but I don&#8217;t know how well it works. I don&#8217;t like zc.buildout quite as much as virtualenv, and I see that people even use virtualenv+zc.buildout to eliminate site-packages from leaking in. I also find that it leaves tons of old packages around in every buildout, again with no way to manage them.

What I&#8217;ve found using both zc.buildout and pip is that they are _slow and annoying_, because they&#8217;re constantly reinstalling things that I already have. The main reason for having a shared site-packages as I suggest above is not to save on disk space, but to save on _time_. In development, I want to be able to update to the latest versions of packages quickly, installing/building only the ones that have changed. How fast something runs changes how you use it, and I know that the scripts that I have for updating development and production environments reflect that.

So,I think the main thing that I&#8217;m looking for is a new tool to manage the packages that I have installed globally and within virtualenvs. Are there tools out there that are heading down this path at all?

Also, I understand the starting point that [Tarek][7] is taking with [Distribute][8] (splitting it up into logical pieces), but is there any roadmap for where it&#8217;s going to go functionally from there? Or is the intention purely that tools like the one I&#8217;m angling for will be written against the newly refactored libraries? I do know about the uninstall PEP, and that&#8217;s pleasing.

 [1]: http://pypi.python.org/pypi/virtualenv
 [2]: http://pip.openplans.org
 [3]: http://pypi.python.org/pypi/zc.buildout
 [4]: http://www.blueskyonmars.com/projects/paver/
 [5]: http://groups.google.com/group/python-virtualenv/browse_thread/thread/82911e7fc9901045
 [6]: http://pypi.python.org/pypi/buildout.dumppickedversions/0.4
 [7]: http://tarekziade.wordpress.com/
 [8]: http://pypi.python.org/pypi/distribute/0.6