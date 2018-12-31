---
title: Test driving Brackets
author: Kevin Dangoor
type: post
date: 2013-01-02T20:01:17+00:00
url: /2013/01/02/test-driving-brackets/
categories:
  - Brackets

---
I got [test infected][1] a number of years ago, so it was perfectly natural for me to want to test-drive changes to [Brackets][2], now that I&#8217;m back into writing code. In fact, I had a perfect bug to work on for test-driven development: [improving the QuickOpen heuristics][3]. This code needs to be able to return proper matches with reasonable scores, something that is very easily tested.

When I started working on this bug, QuickOpen did not have any tests. Additionally, running the tests required reaching for the mouse _every single time_. That&#8217;s more irritating than you might expect if you&#8217;ve never done test driven development. So, I created a Brackets extension called [TestQuickly][4] that lets me run tests appropriate for the current file with a quick keystroke. I made the QuickOpen.js and QuickOpen-test.js files both run the QuickOpen test suite when I hit that key with the file open.

After that bit of setup, I had to start writing tests for the QuickOpen (there weren&#8217;t any tests already) and I had to learn [Jasmine&#8217;s][5] style as well. Writing the tests proved to be straightforward indeed. Alas, improving the QuickOpen heuristics was not quite so easy, but the new results are much better. You can take a look at the code I ended up with in [this commit][6].

I made a screencast with a quick demo of the workflow I used:

{{< youtube ba_ZZkMnDU8 >}}

 [1]: http://c2.com/cgi/wiki?TestInfected
 [2]: http://brackets.io
 [3]: https://github.com/adobe/brackets/issues/2068
 [4]: https://github.com/dangoor/TestQuickly
 [5]: http://pivotal.github.com/jasmine/
 [6]: https://github.com/adobe/brackets/commit/e654d09bf7a5ac4084e1235919263c95b93b757e