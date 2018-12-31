---
title: 'Nose and Decorators: be careful!'
author: Kevin Dangoor
type: post
date: 2008-07-26T03:50:58+00:00
url: /2008/07/25/nose-and-decorators-be-careful/
categories:
  - Python
tags:
  - nose
  - testing

---
One theory of unit testing is that your tests should all be entirely independent. I&#8217;ve heard that Google actually has a test runner that randomizes the order of the tests on each run, so you&#8217;re guaranteed that they&#8217;re independent (otherwise they fail).

I want my test _files_ to be independent, but I find that having one test lead into another is often a good way to reuse fixture and avoid making my test fixture more complicated than it needs to be.

[Nose][1] (and [py.test][2]) make this really easy, because they run the tests in the order in which they appear in the file. (Note that if you&#8217;re using Nose to run unittest.TestCases, those tests still run alphabetically as they do under Python&#8217;s built-in test runner). The file order running of tests is very natural and leads to few surprises. It&#8217;s very easy to make a string of tests that build up a nice, complicated fixture testing little pieces as they move along. I&#8217;ll mention that _most_ of my tests will actually run just fine in any order, but I like being able to count on the order when it&#8217;s handy to do so.

All of that is a lead-in to my fun from today. I&#8217;m using Fuzzyman&#8217;s [Mock][3] module to drop in stand-ins for things that are annoying to test. Mock comes with a handy @patch decorator that will replace the callable of your choice with a Mock on the way in, and restore it automatically on the way out. It works great and is really easy to use.

I was thrown off for a bit today because I put a @patch on one of my test functions, and it started failing because a file that it expected to see did not exist! Removing the decorator brought the file back. That file was created in a test function earlier in the file.

If you&#8217;re nodding knowingly at this point, you&#8217;ve probably worked with decorators a fair bit before. I&#8217;ve been known to use [more than my fair share of decorators][4]. I&#8217;ve found that while the syntax is great, some of the side effects can be really annoying. That&#8217;s why [Paver][5]&#8216;s decorators aren&#8217;t true decorators. They just register behavior rather than replacing the function object.

So, what&#8217;s the relationship between using a decorator and the file-based ordering of tests? To sort by file order, Nose looks at the test function&#8217;s func\_code.co\_firstlineno. In the case of ,my test today, that was around 250. However, when I applied the patch decorator, the function was no longer my original function&#8230; it was the function that Mock&#8217;s decorator returned (the one that does the nifty swapping in and out of the Mock). That was around line 97 of mock.py.

When Nose went to sort the functions by func\_code.co\_firstlineno, after decoration my test function was thought to be at line 97. I naively thought that I&#8217;d just change func\_code.co\_firstlineno. Nope, read only. Then I tried sticking an object in place of func\_code that returned the value I wanted for co\_firstlineno. Nope, func_code _has_ to be a &#8216;code&#8217; object.

Luckily, Nose itself has a solution to this problem. The function object can have a &#8216;compat\_co\_firstlineno&#8217; attribute on it, and that attribute will be used instead of func.func\_code.co\_firstlineno. A one-line change to mock.py was all it took.

 [1]: http://www.somethingaboutorange.com/mrl/projects/nose/
 [2]: http://codespeak.net/py/dist/test.html
 [3]: http://www.voidspace.org.uk/python/mock.html
 [4]: http://docs.turbogears.org/1.0#controller-decorators
 [5]: http://www.blueskyonmars.com/projects/paver/