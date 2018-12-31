---
title: TurboGears now supports Cheetah and Stan
author: Kevin Dangoor
type: post
date: 2006-01-01T15:28:10+00:00
url: /2006/01/01/turbogears-now-supports-cheetah-and-stan/
categories:
  - Python
  - TurboGears

---
The other day, I talked about [what TurboGears is not][1], specifically mentioning template systems. TurboGears has one documented, supported and included way for generating pages: [Kid][2]. But, with the latest code in Subversion, TurboGears now also supports [other template engines via plugins][3] that provide fairly seamless support for other systems.

Which other systems? There are already two plugins, and writing plugins is easy (and [documented][3]).

[TurboCheetah][4] provides support for, you guessed it!, [Cheetah][5]. Since that one is in the Cheeseshop, you can get it just by running &#8220;easy\_install TurboCheetah&#8221;. If you run &#8220;easy\_install -f http://www.turbogears.org/download/ TurboCheetah&#8221;, you can even get prebuilt eggs for Cheetah 1.0 for Windows and Mac.
  
Cliff Wells has written [a plugin for Stan][6]. Once he gets that up on the Cheeseshop, that will be easy_installable as well.

<!--adsense-->

 [1]: http://www.blueskyonmars.com/2005/12/20/what-is-turbogears-not/
 [2]: http://kid.lesscode.org
 [3]: http://www.turbogears.org/docs/plugins/template.html
 [4]: http://cheeseshop.python.org/pypi/TurboCheetah
 [5]: http://www.cheetahtemplate.org
 [6]: http://blog.develix.com/archive/2006/01/01/stan-turbogears-continued/