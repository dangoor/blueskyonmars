---
title: Idiomatic python vs. idiomatic Java
author: Kevin Dangoor
type: post
date: 2004-12-03T20:09:06+00:00
url: /2004/12/03/idiomatic-python-vs-idiomatic-java/
categories:
  - Software Development

---
Phillip Eby came across a Python app developed by Java folks and wrote about what he saw: [dirtSimple.org: Python Is Not Java][1]. I agree with his points, except the one about XML.

I don&#8217;t think XML should be used for a lot of the things it&#8217;s used for in Java. XML APIs in Java are generally quite painful to work with. If you need a little bit of dynamic nature in your Java app, use BeanShell, Groovy or Jython.

And don&#8217;t use XML as your data model. Ick. Use Java objects! XML is a great interchange format&#8230; leave it where it belongs.

 [1]: http://dirtsimple.org/2004/12/python-is-not-java.html "dirtSimple.org: Python Is Not Java"