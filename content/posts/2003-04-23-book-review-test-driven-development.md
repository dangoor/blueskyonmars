---
title: 'Book Review: Test Driven Development'
author: Kevin Dangoor
type: post
date: 2003-04-23T21:40:21+00:00
url: /2003/04/23/book-review-test-driven-development/
categories:
  - Reviews
  - Technology

---
<a HREF="http://www.amazon.com/exec/obidos/ASIN/0321146530/blueskyonmars-20"><br /> Kent Beck&#8217;s Test Driven Development: By Example</a> follows the mold of the XP books: fairly thin and $30. I&#8217;ve never read Beck&#8217;s XP book, but I&#8217;ve read a couple of the others. Those books all seem to rehash the same material. Thankfully, this book is not like that.
  
<!--more-->


  
For people who&#8217;ve never done TDD: the idea is simple. You take tiny steps with your code, writing a test for something you want to accomplish, making the test pass as quickly as possible, and then removing any duplication of code that resulted. Beck calls this cycle &#8220;Red-Green-Refactor&#8221;, based on JUnit&#8217;s GUI that shows red for failing tests and green for passing ones.

I found this book to be useful and nicely designed. The first part of the book walks through a couple of example programs that are built up bit-by-bit. These examples provide a look into Beck&#8217;s style of producing code and take the notion of TDD from the theoretical to the practical.

The other major part of the book goes over design patterns and testing strategies. When you actually start doing TDD, you often find that certain constructs are not easy to test. Beck provides tips on testing different types of components. The general pervading philosophy is that if something is very difficult to test, it&#8217;s probably not designed correctly. Fix the design, and you should be able to write your tests.