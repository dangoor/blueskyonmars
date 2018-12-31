---
title: Eclipse 3.0 on the way
author: Kevin Dangoor
type: post
date: 2003-05-23T16:34:55+00:00
url: /2003/05/23/eclipse-30-on-the-way/
categories:
  - Software Development

---
According to the latest [Eclipse Project Draft 3.0 Plan][1], 3.0 Milestone 1 is scheduled to be released June 6th! Of course, their release plan goes all the way up to M5 in November, but still it will be great to start seeing new Eclipse features showing up. Here are the things that interest me most that are committed for 3.0:

  * Lots of editor improvements including more typing actions, better integrated key bindings, folding in the editor window and splitting of the editor window to edit different parts of the same document
  * Make Eclipse usable as a rich client platform, not just for IDEs. Plug-ins, help system, update manager all will be packaged for use in other programs.
  * Support Java and Java references in other files (like JSP and SQLj, and references to classes that appear in xml files)
  * Present a logical view of the objects in the debugger (so a HashMap appears as key/value, not just a java.util.HashMap)

The following are some nifty &#8220;proposed&#8221; items for 3.0, which means they don&#8217;t have a specific solution yet.

  * Be able to open files outside the workspace! &#8211; I can understand why this is tricky (do those files compile? If so, where to?), but it would still be nice to be able to use the Eclipse editor for other, non-managed files.
  * HTML widget that works on all platforms
  * Automatic synchronization with filesystem changes
  * Plug-ins can be added/removed dynamically
  * Better interoperability between Swing and SWT
  * Support for J2SE1.5 &#8211; I really hope generics makes it into an early Eclipse release, because I&#8217;d like to start using them. There are all ready reliable ways to compile 1.5 generics for use in current JVMs

Lots of good stuff coming down the line, and the number of plug-ins grows all the time. Eclipse shows just how good an open source project can do when it has a bit of money backing it!

 [1]: http://www.eclipse.org/eclipse/development/eclipse_project_plan_3_0.html "Eclipse Project Draft 3.0 Plan"