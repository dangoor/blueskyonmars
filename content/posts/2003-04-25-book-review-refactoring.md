---
title: 'Book Review: Refactoring'
author: Kevin Dangoor
type: post
date: 2003-04-25T21:35:08+00:00
url: /2003/04/25/book-review-refactoring/
categories:
  - Reviews
  - Technology

---
I have finally gotten around to reading <a HREF="http://www.amazon.com/exec/obidos/ASIN/0201485672/blueskyonmars-20">Martin Fowler&#8217;s <i>Refactoring: Improving the Design of Existing Code</i></a>. In fact, I&#8217;ve also just gotten around to reading the Gang of Four <a HREF="http://www.amazon.com/exec/obidos/ASIN/0201633612/blueskyonmars-20">Design Patterns</a> book. These two books belong on every OO programmer&#8217;s bookshelf.
  
<!--more-->


  
Refactoring is the art of improving software. Before the Fowler book, it was almost completely art. With this book, there&#8217;s a bit more science to it. The largest section of the book is a catalog of Refactorings: systematic changes you can make to your programs to make them more reusable and easily understood.

The book starts off with introductory text that describes the point of refactoring and gives some examples to make it clear how they&#8217;re really applied. I liked the discussion of &#8220;code smells&#8221;, because I think that&#8217;s a good way to describe the feel of code that may be in need of some change.

Many of the refactorings may seem obvious if you&#8217;ve been programming a while. But, that&#8217;s part of the point: these are things that experienced programmers may do naturally. Just as the GoF cataloged the patterns that are commonly used and described how and when to use them, Fowler has taken these refactorings and made their usage explicit.

One refactoring that seems so simple but just hadn&#8217;t occurred to me before was &#8220;Null Object&#8221;. Though Java protects the programmer from stepping into memory locations they shouldn&#8217;t be, it doesn&#8217;t protect from accessing object references that are null. So, if you&#8217;re being safe in your code, you end up with all sorts of if (foo == null) lines in your code. The Null Object refactoring introduces an object that provides a safe value to work with. This is particularly useful when it comes to JSPs or other templates: your null object could provide default values for those particular fields. Certainly, these values appearing still represent some kind of error condition, but at least you can be sure that the user will get a nicer looking page from your webapp than a &#8220;500 Servlet Exception&#8221; with an icky traceback.

One added bonus to the Refactoring book is that IDEs like [Eclipse][1] have the ability to automatically, mechanically apply some of the refactorings for you. The names Eclipse uses for the refactorings are straight from Fowler&#8217;s book.

Design Patterns by the GoF and Refactoring by Fowler both belong on any OO programmer&#8217;s bookshelf. They provide useful terminology for solutions to common problems.

I&#8217;m hoping to soon read Fowler&#8217;s newer Patterns of Enterprise Application Architecture.

 [1]: http://www.eclipse.org