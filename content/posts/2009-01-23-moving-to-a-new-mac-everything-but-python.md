---
title: 'Moving to a new Mac: everything but Python'
author: Kevin Dangoor
type: post
date: 2009-01-23T13:39:32+00:00
url: /2009/01/23/moving-to-a-new-mac-everything-but-python/
categories:
  - Python

---
With my new job comes a new MacBook Pro (the latest generation, very slick!). The Setup Assistant did a great job of making my new MBP just like my old one, carrying across all of my applications and settings from my latest Time Machine backup. Everything in /usr/local/bin made it. Ditto for my MacPorts stuff in /opt.

One thing that didn&#8217;t make it was the Python libraries that I had installed in the system-wide site-packages directory (/Library/Python/Version/2.5/&#8230;). The Setup Assistant is designed to not pull OS parts across when you are loading up a new machine. That makes sense, but unfortunately the Python stuff seems to fall into that category.

Perhaps the site-packages directory should be moved to /usr/local or something so that it gets copied over? A change like that would be useful for Apple to make.

Thankfully, the impact on me is pretty minimal, because I tend to do my work in virtualenvs and don&#8217;t have very many packages installed system-wide.