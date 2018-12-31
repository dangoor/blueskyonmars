---
title: Simple tool for finding Swing threading mistakes
author: Kevin Dangoor
type: post
date: 2004-08-24T19:42:08+00:00
url: /2004/08/24/simple-tool-for-finding-swing-threading-mistakes/
categories:
  - Software Development

---
Scott Delap provides a nice, simple way to [Easily Find Swing Threading Mistakes][1]. It involves a replacement RepaintManager that confirms that repaints are all taking place on the Swing event dispatch thread. Nice solution.

(You&#8217;ll note from the comments and the followup article that this solution isn&#8217;t perfect&#8230; but that doesn&#8217;t mean it&#8217;s not useful!)

 [1]: http://www.clientjava.com/blog/2004/08/20/1093059428000.html "ClientJava.com - Easily Find Swing Threading Mistakes"