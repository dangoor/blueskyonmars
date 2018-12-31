---
title: Project Management with Bug Tracking Software
author: Kevin Dangoor
type: post
date: 2002-01-28T16:52:00+00:00
url: /2002/01/28/project-management-with-bug-tracking-software/
categories:
  - Music

---
In the beginning, there was software. And it wasn&#8217;t good. The users kept calling with reports of bugs in the software. There were so many of these reports, that the developers decided to make a program to track the bugs. This helped to make sure that every bug would be fixed.
  
<!--more-->


  
Then they realized that some bugs were more critical than others, so they added a field to handle priorities. They also found that people were calling in and asking for new features as well, so they started tracking those. Since they had more than one programmer, they added a field to keep track of which programmer was going to fix the bug.

After that, we&#8217;ve got work units (bugs and features), priorities and responsible parties. Hmm&#8230; that&#8217;s starting to sound like a project management tool. Add due dates and dependency information (work unit x can&#8217;t be completed until work unit y is done) and you&#8217;ve basically got MS Project without the Gantt charts.

To my mind, though, there is one more layer that would be useful in making bug tracking software a complete project management system for software developer (or, arguably, almost anything else): tasks. A given work unit may have multiple parts to get done in order to be complete: back end programming, front end design and documentation. Each of these tasks has a certain amount of work associated with it, and a person responsible for getting that work done. If you add up all of the tasks for a work unit, you can get a good idea of how long that will take to implement. Add expected completion dates, and you can build a complete schedule for an entire software release.

I believe the Mozilla people probably would just open multiple bugs in their database, rather than building the second level of tasks. I think this adds a lot more clutter, though. By having tasks that are distinct from work units (bugs), then you can easily build a nice, high level list of features implemented and bugs fixed in a given release.

It&#8217;s interesting to note that MS Project works like an outliner, thereby providing this same kind of feature. It ends up being not entirely surprising that bug tracking systems are looking more like project management systems. But, I think many bug tracking systems are easier to use and provide better group communication.