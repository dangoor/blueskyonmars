---
title: Building the Firebird Database on Mac OSX Tiger
author: Kevin Dangoor
type: post
date: 2005-06-23T19:57:29+00:00
url: /2005/06/23/building-the-firebird-database-on-mac-osx-tiger/
categories:
  - Software Development

---
The folks who make the [Firebird][1] database only package up the &#8220;classic&#8221; server for the Mac. This is a process-based server and is more resource intensive than the multithreaded SuperServer. David Pugh has written up instructions for [building a Firebird SuperServer on Mac OS X][2].

I have a couple of additions for people using Tiger. First, you&#8217;ll need to gcc_select 3.3, because Firebird does not appear to be gcc 4.0 compatible at this point. 

The next thing needed for Tiger is to include the SystemStubs library. If you search the configure.in file for CoreFoundation, you&#8217;ll find the line you need to change. Add a &#8220;-lSystemStubs &#8221; in front of the -framework and you should be good to go.

 [1]: http://firebird.sf.net
 [2]: http://homepage.mac.com/david.pugh/FirebirdOSX/FirebirdDatabaseonOSX.html