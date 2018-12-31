---
title: A brief history of TurboGears
author: Kevin Dangoor
type: post
date: 2005-09-24T04:30:14+00:00
url: /2005/09/24/a-brief-history-of-turbogears/
categories:
  - Python
  - TurboGears

---
An email from Jimmie Houchin has convinced me to take a few minutes out and explain where [TurboGears][1] came from and why it has emerged on the scene now. One note about how I&#8217;m writing this: there are many good tools for Python that solve a variety of needs. Since I&#8217;m not out to disparage other people&#8217;s work here, I&#8217;m not going to mention tools that I had been using or tools that I decided not to use.

In December, I decided to build Zesty News in Python after considering _several_ alternatives (Rails, Seaside, Java-based tools). Python had nothing as slick as Rails for doing webapp development, but it had a whole bunch of great tools for other parts of my application.

I started working in earnest on [Zesty News][2] in January. I had to go through the same collection of reading about and deciding on pieces of the puzzle that everyone does when they start creating a webapp. (Side note: Zesty News is a &#8220;desktop webapp&#8221;&#8230; users install it on their machine and it runs a webserver to provide the bulk of the UI.)

I chose the tools that seemed, after a little digging, to be the best combination. The only one of those tools that is part of TurboGears is SQLObject. Development proceeded fairly smoothly until May, and then [a funny thing happened on the way to release][3]. I changed gears and decided to strongly emphasize plugins within Zesty News.

That notion changed the direction of things considerably. I wanted to provide a great API for building plugins, as this would benefit me (the full version of Zesty News will be built as plugins on top of the free version) and everyone who wants to customize the program. Toward the end of May, [CherryPy][4] became my web framework of choice.

In June, I dealt with a bunch of database nastiness that I never would&#8217;ve had to deal with if Zesty News was purely web-based and not a desktop app. Once I left that behind and got back to business, I realized that I would have to get together some decent documentation on the framework I was using to show people how to build plugins. I figured that if I&#8217;m doing that work anyway, I might as well package everything up conveniently and make the whole thing one nice, tidy open source package. That was around the end of June or early July.

Around that time, I started pestering [Phillip Eby][5] on the distutils-sig list about [Python Eggs][6]. I knew that something would have to be done to make TurboGears install easily, and Phillip had a rapidly maturing answer to that problem.

Then, [Bob Ippolito][7] started [teasing us][8] with promises of a [cleaner JavaScript framework][9]. I pestered him to give me a preview and had soon replaced my other JavaScript framework with MochiKit.

Bob was extolling the virtues of attribute-based templating languages when I took another look at [Kid][10]. My first look at Kid had been much earlier in the year, and I wasn&#8217;t particularly impressed. When I looked again in July, I knew I had found the ultimate: easy and Pythonic, yet fully valid XML and viewable in the browser. It didn&#8217;t take me long to rip out my old templates and replace them with shiny new Kid ones.

After the release of the first Zesty News alpha, I turned my attention to preparing TurboGears for release. I went through some effort getting API docs together using a hacked epydoc that includes colorized source files. I cleaned up the code that creates the Blazing Things website and turned it into docgen.py that appears in TurboGears.

And, of course, I wrote, and setup servers and got domains, and figured out how to do a screencast and all that good stuff. Which is how we got to where we are today&#8230;

I&#8217;ve actively used different tools for all of the parts of TurboGears and read extensively about many more. I&#8217;m happy to have found a great set of tools that work well together, and it&#8217;s gratifying to know that I&#8217;ve helped other people to use them as well.

(Not such a brief history, huh? Unfortunately, I didn&#8217;t have time to make it shorter (paraphrasing Blaise Pascal).)

 [1]: http://www.turbogears.org
 [2]: http://www.zestynews.com
 [3]: http://www.blueskyonmars.com/2005/08/18/a-funny-thing-happened-on-the-way-to-release/
 [4]: http://cherrypy.org
 [5]: http://dirtsimple.org
 [6]: http://peak.telecommunity.com/DevCenter/setuptools
 [7]: http://bob.pythonmac.org
 [8]: http://bob.pythonmac.org/archives/2005/07/01/javascript-frameworks/
 [9]: http://www.mochikit.com/
 [10]: http://kid.lesscode.org