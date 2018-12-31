---
title: Eclipse 3.0M6 classloader is a little wonky
author: Kevin Dangoor
type: post
date: 2004-01-06T18:15:43+00:00
url: /2004/01/06/eclipse-30m6-classloader-is-a-little-wonky/
categories:
  - Software Development

---
I had a BeanShell script to configure a Hibernate Session that was working before Christmas. It stopped working, and I just traced the problem to Eclipse.

For those of you following the Eclipse 3.0 track, there appears to have been an odd change to the classloader that can cause problems under certain circumstances&#8230; In 3.0M5, SomeClass.class.getClassLoader() returns a reasonable classloader. In M6, that returns null, which can certainly throw things off when they&#8217;re expecting a valid classloader.

Hibernate&#8217;s Configuration.addClass method calls getClassLoader().getResourceAsStream(&#8230;) on the class you pass in. Obviously, this will give you a null pointer exception of the classloader returned is null&#8230; gah.