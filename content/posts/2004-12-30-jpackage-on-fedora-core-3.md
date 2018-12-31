---
title: JPackage on Fedora Core 3
author: Kevin Dangoor
type: post
date: 2004-12-30T20:23:44+00:00
url: /2004/12/30/jpackage-on-fedora-core-3/
categories:
  - Java

---
I wanted to install Tomcat and ant on my new Fedora Core 3 box. Installing Tomcat failed, because I was missing jta. Since jta is a non-free package, you need to jump through some hoops.

So, I jumped the hoops and then jta was complaining about missing java-devel. I had actually installed J2SDK from Sun&#8217;s RPMs. I decided to go the full-blown JPackage route and install the J2SDK _their_ way. Fine and dandy. Except, the RPMs built via the JPackage build process wouldn&#8217;t install! They complained about not having the Java .so files (but I thought that&#8217;s what I was installing!). Michael Peters to the rescue: [Java in Fedora Core 3][1] mentions this problem, and he provided a SPEC file to fix this.

Sadly, I was still missing a library that java wanted. Michael Peters&#8217; page also listed the magic incantation to get Sun&#8217;s RPM working with JPackage: yum install java-1.4.2-sun-compat. I missed that on the JPackage site.

 [1]: http://mpeters.us/linux/j2sdk.php "Java in Fedora Core 3"