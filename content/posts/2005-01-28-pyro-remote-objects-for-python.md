---
title: 'Pyro: remote objects for Python'
author: Kevin Dangoor
type: post
date: 2005-01-28T16:36:05+00:00
url: /2005/01/28/pyro-remote-objects-for-python/
categories:
  - Python

---
I&#8217;m sure that this is old news for everyone else, but it&#8217;s new to me. Look at the features of [Pyro][1], Python Remote Objects. Wow. If you think Python would save you a lot of code and hassle compared to Java, that&#8217;s nothing compared to the pain that Pyro would save you over Java&#8217;s RMI! I don&#8217;t think I need Pyro right this second, but I have no doubt that I&#8217;ll be using this at some point. It also looks like Pyro already handles what [Py.Execnet][2] is trying to do with remote code running. The Pyro features list says that it can send objects across the wire, even including the Python bytecode if necessary. (The security implications there are staggering&#8230; but, the feature would be very powerful in a closed environment.)

(updated to fix idiotic typos)

 [1]: http://pyro.sourceforge.net/features.html "Pyro - Features"
 [2]: http://codespeak.net/py/current/doc/execnet.html