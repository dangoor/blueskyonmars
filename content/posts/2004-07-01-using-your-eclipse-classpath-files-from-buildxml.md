---
title: Using your Eclipse .classpath files from build.xml
author: Kevin Dangoor
type: post
date: 2004-07-01T15:29:08+00:00
url: /2004/07/01/using-your-eclipse-classpath-files-from-buildxml/
categories:
  - Software Development

---
Some nameless person says that you should [JavaGu(i)(y): Stop adding Eclipse .classpath and .project files to cvs!][1]. Most of the comments in reply to this say that you _should_ check those files in and use Eclipse&#8217;s mechanisms for dealing with variations (classpath variables and the like).

I agree that you should check these files in. We&#8217;ve gone even farther than that. Our ant build.xml file has a little piece of Groovy script that reads the .classpath file to set the classpath for the build. That way, we only have one classpath (Eclipse&#8217;s) to maintain. We also generate a JNLP file from the .classpath. This setup works great for us. Eclipse works easily when you check the project out, and our Solaris build server running anthill can run the builds without worrying about syncing up the classpaths.

 [1]: http://weblog.isallineed.net/javagui/archives/000096.html "JavaGu(i)(y): Stop adding Eclipse .classpath and .project files to cvs!"