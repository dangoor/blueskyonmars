---
title: Frameworks matter, too
author: Kevin Dangoor
type: post
date: 2006-01-05T15:36:40+00:00
url: /2006/01/05/frameworks-matter-too/
categories:
  - Python

---
Peter Hunt puts the focus on successful web applications in [How Python wins on the Web][1]. He cites the success of Plone, MoinMoin, Trac, Mailman PyBloxsom and the non-web-based BitTorrent. He cedes the web application framework &#8220;market&#8221; to Rails and suggests that Python will &#8220;win&#8221; by having the best apps out there. I think he&#8217;s half correct. Ultimately, it&#8217;s the apps that people use and having the best apps will increase Python&#8217;s user base. But, the frameworks do matter, too.

The types of apps that Peter is talking about are &#8220;canned&#8221; apps. Install them, tweak some settings and go. But, there are _many_ apps out there that need to be custom written for the task. By saying that &#8220;We won&#8217;t win in the Rails generation&#8221;, Peter says that we might as well give up on frameworks because the custom apps are going to be written in Rails.

I think he&#8217;s wrong. Java, PHP and ASP _dwarf_ Python and Ruby in usage. People using those languages are starting to seriously look at doing things in a more agile way (in the case of Java and C#) or in a more structured way (in the case of PHP). Python, overall, has far greater usage than Ruby. Despite Python&#8217;s deeper penetration, people have been choosing to code their apps in Ruby _because of Rails_. For custom apps, clearly, the framework matters. Rails helps people get their work done faster. Give people a similarly productive experience in Python, and you&#8217;ll attract Python people and Java/PHP people who need to code the many custom apps that need to be written. I have seen this to be the case on the TurboGears mailing list.
  
If I suddenly said, &#8220;oh, Peter&#8217;s right. I&#8217;ll just start coding custom apps in Rails and drop this whole TurboGears thing&#8221;, then of course all custom development would go to Rails. (Except for the fact that TurboGears has achieved enough mass that it would go on without me&#8230;) But, I like programming in Python. Lots of other people do, too. And I want to have a productive time programming in Python. So, there&#8217;s value in a framework like TurboGears.

Back to the canned apps of the sort that Peter was talking about. He&#8217;s right that <span style="font-style: italic">today</span> Python has more successful canned apps out there than Ruby does. But, Rails makes programming an application easier than doing everything ad-hoc. If all of the Python apps continue to be ad-hoc, how will they keep up with folks that are getting things done more quickly with Rails? There are wikis, blogs and even a Trac-like system written in Rails. If those developments move at a higher velocity than the Python ones, eventually they&#8217;ll take over. Once upon a time, I used Movable Type for my blog. WordPress came along with a nicer interface (and an easy migration) and now I&#8217;m running WordPress. There&#8217;s no reason to assume that the existing successful Python projects will remain so indefinitely. (They certainly can, if they continue to be great at what they do!)
  
Many people have written about how much they enjoy using TurboGears and how they get things done quickly. Many of those people are writing custom apps, so clearly Rails isn&#8217;t getting everyone. Additionally, canned apps written with TurboGears are starting to appear. There are developments going on with CherryPy that will make it easy to wire up TurboGears apps easily and naturally <span style="font-style: italic">and</span> to use PasteDeploy if you want to run a non-TurboGears app next to it.

In summary, applications are ultimately what matter. The whole point of a framework is to help people make their apps more quickly. In that regard, frameworks do matter, too.

 [1]: http://www.aminus.org/blogs/index.php/phunt/2006/01/04/how_python_wins_on_the_web