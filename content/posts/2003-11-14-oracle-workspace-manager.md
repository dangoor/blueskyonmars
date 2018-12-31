---
title: Oracle Workspace Manager
author: Kevin Dangoor
type: post
date: 2003-11-14T21:45:24+00:00
url: /2003/11/14/oracle-workspace-manager/
categories:
  - Software Development

---
Today, I came across the [Oracle Workspace Manager][1] and almost literally stood up and said &#8220;wow!&#8221;. Has anyone out there used this beast? Assuming it has good performance characteristics, it sounds fantastic for the kinds of things I&#8217;m working on.

The brief summary, for those who don&#8217;t feel like reading the whole datasheet, is that Workspace Manager provides row-level version control for your database, will branching/merging capabilities and flexibility in terms of which tables are versioned and how they are versioned. The &#8220;how&#8221; can be keeping all changes to a row, or keeping just the most recent change within the workspace. Using the latter, you could just hold on to periodic milestones of the data.

I guess there really is a reason that Oracle costs big bucks and MySQL and PostgreSQL are free. MySQL works great for a great many applications, but there&#8217;s probably no substitute for Oracle in places where Workspace Manager are called for. (Does anyone know of other databases that have this kind of versioning?)

 [1]: http://otn.oracle.com/products/workspace_mgr/htdocs/Workspace_Manager_DataSheet92.html "***Oracle Workspace Manager***--Data Sheet--Oracle Corporation"