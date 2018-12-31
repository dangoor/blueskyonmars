---
title: Don’t import inside of PyObjC actions
author: Kevin Dangoor
type: post
date: 2005-01-15T00:00:34+00:00
url: /2005/01/14/dont-import-inside-of-pyobjc-actions/
categories:
  - Python

---
Bob Ippolito came to my rescue today. I started using Cheetah for some template work, and it turns out that doing:

> from Cheetah.Template import Template

from within your action is bad. (Bus Error bad, not simple exception bad.) So, if you&#8217;re using PyObjC, make sure you do your imports at the module level, not in a given block of code.
  
**Update:** Bob tracked it down. Don&#8217;t import _Cheetah_ inside of an action, because it will import PyObjC&#8217;s WebKit (thinking that it&#8217;s getting WebWare&#8217;s WebKit) and importing PyObjC&#8217;s WebKit inside of an action has some issue at present. So, go ahead and do imports wherever you want again, as long as it doesn&#8217;t involve WebKit 🙂