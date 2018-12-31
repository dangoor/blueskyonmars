---
title: Automatic Python imports with autoimp, lazy ones with Importing
author: Kevin Dangoor
type: post
date: 2006-06-12T15:48:51+00:00
url: /2006/06/12/automatic-python-imports-with-autoimp/
categories:
  - Python

---
[Connelly Blog: Automatic Python imports with autoimp][1] tries to make all modules/packages available without loading everything up. Interesting idea. Something that may also be interesting is using its recursive lazy loader in TG to not import the features you&#8217;re not using. The license is unknown, however. (**Update**: it&#8217;s public domain).
  
**Update**: odd to get two import-related packages in the same day. I&#8217;m uncertain about the automatic import thing, but Phillip Eby just released [Importing][2] which provides dynamic module loading (it also provides &#8220;load object Y from module X specified in python dotted notation string&#8221; utility functions, which could eliminate a utility we have in tg.util.)

 [1]: http://barnesc.blogspot.com/2006/06/automatic-python-imports-with-autoimp.html
 [2]: http://peak.telecommunity.com/DevCenter/Importing