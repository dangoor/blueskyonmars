---
title: Mike Spille’s informative Groovy review
author: Kevin Dangoor
type: post
date: 2004-03-23T04:18:44+00:00
url: /2004/03/22/mike-spilles-informative-groovy-review/
categories:
  - Software Development

---
[Groovy: First Contact][1] provides a detailed look at Groovy&#8217;s features and Mike Spille&#8217;s likes and dislikes thereof. Here was my comment about the review:

Excellent post, indeed.

I think it&#8217;s important for Groovy to have a Java-like syntax, because that makes it easier to move back and forth between the two languages. I also agree that having more than one way to do things is the slippery slope to Perl (resulting in write/execute-only code &#8212; don&#8217;t try to read it).

But, if Groovy is \*too\* close to Java, as I think BeanShell is, you lose part of the reason to have a scripting system at all. The &#8220;->&#8221; and &#8220;.&#8221; thing seems like exactly the kind of thing that will throw Java folks off at first, but is useful when you&#8217;re trying to quickly put a script together. The optional parenthesis and semicolon can be nice for interactive use of a Groovy command line.

I haven&#8217;t looked under the hood, but I wouldn&#8217;t be surprised if operator overloading is used to provide some of the conveniences for Maps and Lists. Sure, you&#8217;ll have someone out there trying to multiply a GIF image by a JDBC ResultSet, but that&#8217;s really their problem. If someList.add(&#8220;foo&#8221;) can be replaced by someList + &#8220;foo&#8221;, I think that&#8217;s a win in a scripting language.

This article is the best one I&#8217;ve seen so far for giving people an idea of whether or not Groovy is for them.

 [1]: http://jroller.com/page/pyrasun/20040321#groovy_first_contact "Groovy: First Contact"