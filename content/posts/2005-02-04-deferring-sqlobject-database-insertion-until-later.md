---
title: Deferring SQLObject database insertion until later
author: Kevin Dangoor
type: post
date: 2005-02-04T16:27:05+00:00
url: /2005/02/04/deferring-sqlobject-database-insertion-until-later/
categories:
  - Python

---
[SQLObject][1] automatically inserts entries in the database as soon as you instantiate them. It also runs updates as soon as you modify attributes. This is not always desirable and [eter Butler has a recipe][2] to choose when to insert and update new objects. It&#8217;s actually not a bad solution, because the object you&#8217;re holding is not truly one of your domain objects. That makes it clearer that something more needs to be done with it. SQLObject _could_ implement this functionality directly with a flag passed to \_\_init\_\_. There is already a flag to defer the updates: just set _lazyUpdate = True on the object, then you need to run syncUpdate or sync to save the data.

 [1]: http://www.sqlobject.org
 [2]: http://sourceforge.net/mailarchive/forum.php?thread_id=6193963&forum_id=30269 "SourceForge.net: sqlobject-discuss"