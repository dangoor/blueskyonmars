---
title: Naked Objects
author: Kevin Dangoor
type: post
date: 2003-06-03T23:21:11+00:00
url: /2003/06/03/naked-objects/
categories:
  - Software Development

---
This is the first time I&#8217;ve come across the [Naked Objects framework][1]. A &#8220;naked object&#8221; is basically a fairly standard Java object that descends from a base class provided by the framework. The interesting bit is what the run time system provides:

>   * A viewing mechanisms that creates, in real time, a user-manipulable representation of any naked object that the user needs to access. The viewing mechanism included with the framework generates the style of user interface shown throughout this site. Alternative viewing mechanisms could generate different styles of interface, and/or interfaces customised to the capabilities of different platforms, channels, or devices.
>   * A persistence mechanism, which renders the naked objects persistent via a specific Persistor class. The framework comes with a very basic Persistor class that stores each naked object as a separate XML file. This is suitable for rapid prototyping, but does not scale up. More sophisticated Persistors have been written to utilise popular middleware such as Enterprise Java Beans, and we expect that alternative Persistors will become publicly available.</blockquote> 
> 
> The Naked Objects site doesn&#8217;t talk about what license the package comes under (and I haven&#8217;t downloaded it yet to find out). This seems potentially useful for me, because the applications I&#8217;m working on are with a controlled user community that can be trained on how to use the system.
  
> **Update 4:24**: just found a reference in the newsgroup that Naked Objects is LGPL.

 [1]: http://www.nakedobjects.org/getting-started.html#getting_started "Getting started with the Naked Objects framework"