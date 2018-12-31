---
title: SQLAlchemy has a release (and a declarative layer)
author: Kevin Dangoor
type: post
date: 2006-02-14T14:52:43+00:00
url: /2006/02/14/sqlalchemy-has-a-release-and-a-declarative-layer/
categories:
  - Python

---
[SQLAlchemy][1], which was announced a couple months back and has been busy in svn, has now had its first release. Congrats to Mike Bayer on that! SQLAlchemy is an object-relational database mapper that uses the [data mapper pattern][2]. This is in contrast to [SQLObject][3] and [ActiveRecord][4] which use the [active record pattern][5]. Also interesting for SQLAlchemy, is that Jonathan LaCour&#8217;s [declarative layer][6] effectively gives you active record-style mapping. The data mapper pattern works well for more complicated databases or bigger databases because it lets you be more explicit about what you want to pull from the database and how you want it to show up in your objects. That flexibility also makes it more complex for simpler tasks. That&#8217;s why I think that Jonathan&#8217;s ActiveMapper strikes a nice compromise.

 [1]: http://sqlalchemy.org/
 [2]: http://www.martinfowler.com/eaaCatalog/dataMapper.html
 [3]: http://sqlobject.org
 [4]: http://wiki.rubyonrails.org/rails/pages/ActiveRecord
 [5]: http://www.martinfowler.com/eaaCatalog/activeRecord.html
 [6]: http://cleverdevil.org/computing/35