---
title: Beware of Java string memory allocation
author: Kevin Dangoor
type: post
date: 2005-04-27T19:57:27+00:00
url: /2005/04/27/beware-of-java-string-memory-allocation/
categories:
  - Java

---
Charles Miller and other Atlassian folks were digging into a memory issue and found out that [memory allocation and garbage collection for Strings and StringBuffers][1] may not be what you&#8217;re expecting. The main thrust of it is that there are some optimizations to speed the common cases that can result in considerable memory waste if you&#8217;re not aware of the implementation. (For example, if you have a StringBuffer with a 32K capacity and do a toString on it, that new String will take up 32K of memory even if you only had 1 byte in the StringBuffer.)

To me, that actually sounds like a bug. It&#8217;s probably worth a couple microseconds (or less) to see if the data is significantly smaller than the allocated space and then do a copy if that&#8217;s the case.

 [1]: http://fishbowl.pastiche.org/2005/04/27/the_string_memory_gotcha