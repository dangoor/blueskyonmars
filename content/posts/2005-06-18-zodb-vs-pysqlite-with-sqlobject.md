---
title: ZODB vs. pysqlite with SQLObject
author: Kevin Dangoor
type: post
date: 2005-06-18T14:15:51+00:00
url: /2005/06/18/zodb-vs-pysqlite-with-sqlobject/
categories:
  - Python

---
I have found only two good options for an embedded, transactional database that can be conveniently used in a non-free Python application: the [ZODB][1] and [sqlite][2]. I started out with sqlite and then recently started doing some heavy duty tinkering with the ZODB.

### Concurrency

For many desktop applications, sqlite is _great_. The data is all conveniently stored in one file and current versions of sqlite even eliminate the need for &#8220;vacuuming&#8221; up deleted data. Add [SQLObject][3] to the mix, and you can get fairly transparent access to the database once you&#8217;ve set up your classes.

The problem that I ran into with SQLite is with concurrency. Concurrency is not much of a problem for many desktop apps: you have one user at the computer doing work, and that&#8217;s it. For my application, the app is doing things in the background and updating the database _while_ the user is using the software. This effectively brings in some of the usually issues you have in a multiuser app.

sqlite has a simple locking strategy: if anyone starts writing executing data update statements in a transaction, the _whole database_ is locked. So, while the background process was updating the database, the GUI would get stuck waiting for it. Ick.

The ZODB, particularly ZODB 3.4, has a great concurrency picture. The current ZODB implementation uses multi-version concurrency control (MVCC). This means that rather than locking the data when a write is occurring, other threads will just get older data. The ZODB doesn&#8217;t do locking at all. Instead, of two threads try to make updates to the same object a Conflict exception is raised for the one that didn&#8217;t make it through. The great thing about this strategy is that you can often just capture that exception and replay the transaction at the application level. This is exactly what Zope does.

In the work that I&#8217;ve been doing with it of late, ZODB 3.4 really does handle concurrency beautifully.

### APIs

The other great thing about the ZODB is that it is _transparent_. There are only a very few things that you would do differently using the ZODB than what you do normally in Python. To save an object to the database, you just need to attach it to an object that is already hanging somewhere off of the root of the database.

SQLObject is a great object-relational mapper (ORM). Once you set up your classes, using SQLObject is about as transparent as an ORM can get. The downside is that you&#8217;re still doing mapping so you can&#8217;t completely forget about the fact that there&#8217;s a relational database back there.

With the ZODB, you can store any objects you need to in there, and you can do convenient Pythonic things, like adding new variables to instances that are stored in the database.

Since it sits on a relational database, SQLObject gives you excellent querying capability out-of-the-box. With the ZODB, you need to use a &#8220;catalog&#8221; to do anything other than what is effectively a &#8220;primary key search&#8221;. The catalog maintains indexes of the objects based on whatever attributes you need to index and will run queries against those indexes. Using the persistent BTrees that come with the ZODB, these indexes are very easy to create.

Note, however, that you need to create these indexes yourself and keep them up to date. [IndexedCatalog][4] can provide a little more of the relational database ease-of-use for searching.

The ZODB comes with a full-text search index, which sqlite does not.

### The downside of ZODB

The ZODB, particularly with MVCC, works great for the application for which is was developed: web sites. The biggest trouble that I have with it for a desktop application is the packing operation required by the FileStorage. FileStorage is by far the most used (and maintained) way to store the database data. I don&#8217;t believe there is presently a maintained storage that does not require packing.

The good thing about packing is that it can happen in the background. The bad thing is that packing a 250MB database file down to 195MB takes many minutes (on my 1.25GHz PowerBook) with the Python process grabbing as much CPU as it can. It&#8217;s fine for a website to do a pack during off-peak hours, but sucking up a desktop user&#8217;s CPU for a good long time is unpleasant.

The ZODB tends to grow more quickly than a relational database does. The ZODB stores pickles of the objects. If you look at how pickles are stored, everything from an object&#8217;s **dict** gets dropped directly into the pickle with both the key and value. This makes sense, because any instance can have any set of attributes in its dict. I noticed that using **slots** does not seem to gain you any extra space efficiency in your pickles. Since a relational database has no such flexibility in storage, it can be far more efficient in space. That 195MB ZODB I mentioned is about 75MB in sqlite. Luckily, disk space is cheap.

ZODB (with FileStorage) uses a bit more memory than sqlite. I believe the current figure is about 8 bytes per persistent object to keep track of where the objects are in the big .fs database file. This is not _too_ onerous. 1 million objects means 8MB of memory used, and machines can readily handle that.

It&#8217;s just worth pointing out that the ZODB is more resource hungry than sqlite.

### Conclusion

Isn&#8217;t computer science great? There&#8217;s very rarely a &#8220;perfect&#8221; solution to a problem. I figured I&#8217;d write this up to help anyone who might be thinking about how they want to store their data in their application. sqlite and the ZODB have some significant differences and choosing one over the other really means taking into account what is most important for your application.

 [1]: http://www.zope.org/Products/ZODB3.4
 [2]: http://sqlite.org
 [3]: http://sqlobject.org
 [4]: http://www.async.com.br/projects/IndexedCatalog/