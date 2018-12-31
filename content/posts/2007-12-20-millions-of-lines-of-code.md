---
title: Millions of lines of code
author: Kevin Dangoor
type: post
date: 2007-12-20T15:36:46+00:00
url: /2007/12/20/millions-of-lines-of-code/
categories:
  - Software Development

---
Steve Yegge attracts some attention with [Code&#8217;s Worst Enemy][1], in which he uses many, many words to say that &#8220;big, bloated software sucks to maintain&#8221;. He talks about a 500,000 line Java-based game that he wrote that is unmanageable. Though he&#8217;s railing against code bloat in general, he does rant a bit about Java in particular. I&#8217;ll come back to Java&#8230;

First off, I agree with the basic idea that having too much code to manage in a single conceptual unit (a program) makes life very difficult.

The first defense against this is good product management. Only add features if they&#8217;re good for the product as a whole. If you strip out a lot of fringe features, you can end up with a much leaner product that is both easier for you to maintain _and_ easier for users to get into using. [Scribbles][2] brings this to mind. The app is focused on creating drawings and provides a UI that is completely streamlined to the task. I would guess that the code for Scribbles is not out of control, because it would be similarly focused.

The next thing to consider is that **we all routinely write 1 million+ LOC programs**. Consider this case:

    
    #!/usr/bin/python
    
    print "Hello, world"
    

Conceptually, programs don&#8217;t get much easier than that. But, running that program and seeing its output in a Terminal.app window on my Leopard-based Mac running Python 2.5 undoubtedly touches at least 100,000 lines of code. The trick is that I have faith that Python, Terminal and Leopard are all going to do their jobs (and those big guys have faith in the libraries they use), so that I can effectively ignore 99,999+ lines of code and just focus on the one.

There were a couple of commenters on Steve&#8217;s blog post that suggested that maybe rather than having a 500,000 line program what he really should have is a 10,000 line program and a bunch of libraries. In one sense, this is the compartmentalization that Steve complains about in his post. Libraries are one effective way of compartmentalizing code that has proven to be very successful over the years.

And language features are another way to segment code. That&#8217;s part of what the recent hubbub over domain specific languages is all about. Libraries can reduce how much you have to think about as you solve a problem, and DSLs can further reduce this.

Which brings me back to Java and Steve&#8217;s original point. We can focus on **reducing the amount of code we manage** by using libraries, and there is certainly plenty of that going on in Javaland. We can also add higher-level features to our languages. Doing so reduces the total lines of code required to solve a problem and the cognitive load required to maintain a program. Here&#8217;s an example:

    
    import time
    
    class Foo(object):
        @property
        def foo(self):
            return time.time()
    

Python&#8217;s attribute and property handling means that you don&#8217;t need to define random setters and getters all over the place. You just define them where you need them. Think about how many lines of code in Java are wasted on getters and setters that do nothing beyond the standard behavior, and how many times you have to type `bar.getFoo()` rather than just `bar.foo`. Yes, I know that Eclipse generates the getters and setters for you, but you still have to read through all of that muck when you&#8217;re trying to figure out what a program does.

In a nutshell:

  * I agree that code bloat is a huge problem
  * I&#8217;m sure that part of the blame for having 500,000 lines of code to manage single handedly rests with Steve&#8230; in choices he made about features to include, and in how he decided to decompose the problem.
  * **But** I also agree that Java carries dramatically higher cognitive load than many other popular languages and one should really think about alternatives.

 [1]: http://steve-yegge.blogspot.com/2007/12/codes-worst-enemy.html
 [2]: http://www.atebits.com/