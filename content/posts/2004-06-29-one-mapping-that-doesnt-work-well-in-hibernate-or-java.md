---
title: One mapping that doesn’t work well in Hibernate or Java
author: Kevin Dangoor
type: post
date: 2004-06-29T16:41:59+00:00
url: /2004/06/29/one-mapping-that-doesnt-work-well-in-hibernate-or-java/
categories:
  - Software Development

---
Hibernate does a good job of managing relationships for you. If your data forms a nice object graph, not only do you not have to write SQL, you don&#8217;t even need to write Hibernate&#8217;s query language! Just traverse your graph and Hibernate will load objects as needed.

I&#8217;ve stumbled across a relationship that Hibernate doesn&#8217;t handle particularly well. Hibernate does a good job of staying true to the semantics of the Java collections framework. The exception to this is their &#8220;bag&#8221;, which is an unordered collection of items that can contain the same item multiple times. They use a List to represent this, but make it clear in the docs that the order is not maintained.

What I need is a little different from anything in java.util&#8230; It needs to be ordered like a List and provide for random access and update of elements like a List. But, any given item should only appear in there once. I tried mapping this with a List (ignoring the only appearing once in the list requirement for the moment) and it _almost_ worked. Updating the list proved to be problematic though (details in this [Hibernate Forum thread][1]). My situation is complicated a little bit by the fact that this is a bidirectional many-to-many relationship that has this interesting collection on one side and a Set on the other.

Remarkably, I&#8217;m [not the only one with this problem][2]. I think that certain piece of data lend themselves to this structure. It would be nice to get a generic solution together for this (after meeting my specific application need, of course 🙂

 [1]: http://forum.hibernate.org/viewtopic.php?p=2207185#2207185 "Hibernate Forums - View topic - PK constraint violated when removing first item from list"
 [2]: http://forum.hibernate.org/viewtopic.php?t=932130