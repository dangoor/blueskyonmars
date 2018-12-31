---
title: “Great Hackers” and XP
author: Kevin Dangoor
type: post
date: 2004-07-30T18:58:23+00:00
url: /2004/07/30/great-hackers-and-xp/
article:
  - 1
categories:
  - Software Development

---
This is my first longish article in a while. Paul Graham has written another interesting piece: [Great Hackers][1]. In it, he describes the care and feeding of &#8220;great hackers&#8221;, the coders who are multiples more productive than the average. I agree with him in general about providing an environment where great hackers can thrive. He glosses over the business needs a bit, I think, but is otherwise on target. The [Slashdot thread][2] broke into the usual language wars, which miss Graham&#8217;s point. That wouldn&#8217;t be the first /. thread to miss the point of the article.

Those who have been reading my blog for a while know that I&#8217;m a supporter of extreme programming (the original XP). I&#8217;ve had successful experiences with XP and have seen environments where XP is clearly a good way to go. I&#8217;ve also been programming on my own for a long time and know very well the feeling of &#8220;flow&#8221; or being &#8220;in the zone&#8221;. Graham&#8217;s article has helped me to reconcile the &#8220;Great Hackers&#8221;/Peopleware mindset with the XP collaboration/pairing mindset.

I&#8217;ve been doing pair programming 100% of the time for several months now&#8230; err, kinda. I&#8217;ve been pairing 100% of the time I&#8217;m in the office. For some of the more interesting and tricky things, I would think about them on the bus or at home. I&#8217;d work through some ideas (sometimes writing the actual code), and then talk to my pair about that the next day.

Creating software sometimes requires intense concentration and creativity. The pair programming way _sometimes_ yields good solutions by having two people brainstorm on the problem. Other times, thinking about the problem independently works best.

So, how do great hackers fit in to an XP shop? _Do_ they fit in?

Let me start to answer that by going back to the business needs that Graham glossed over. In order to be a viable business, you have to produce product (and product that people want). The only way for a great hacker to work on precisely what they want to work on is if they are (1) financially independent, or (2) want to work on something that people are willing to pay for. So, the trick is for them to go work for a company that does things that interest them.

I&#8217;m going to switch now from the term &#8220;great hacker&#8221;, which implies to me someone who puts together a thing of beauty that may or may not have application in the &#8220;real world&#8221;. The term I&#8217;ll use instead is that rather stuffy sounding &#8220;senior engineer&#8221;. Senior has nothing to do with age or years of experience. It has everything to do capability. Senior engineers are great hackers who recognize that they also need to do their part to make the business succeed.

Most products take more effort to develop than a single person (even a senior engineer) can manage. So, the senior engineer can&#8217;t work in a vacuum. Graham did mention this when he talked about the hackers making the engine that the others customize to produce the end product. Since there will most likely be multiple people working on a project, there needs to be a common or at least compatible toolchain used. Maybe that&#8217;s where SOAP and the CLR came from: hackers want to use their language of choice, while letting others in the organization use what they produce.

Businesses also need to be able to ensure the long term viability of their code base. Or, at least ensure that the code can be worked with if their senior engineer were to leave the company. This is where XP&#8217;s test driven development, collective code ownership and pair programming fit in. Unit tests describe what the code is supposed to do and ensure that it does it (so much so, that [Hausfolk have made a project with that slant][3]). Unlike normal written docs, unit tests have to keep up with the code.

I&#8217;ve worked in organizations with huge towers of knowledge. If someone leaves the company, written documentation sucks as a way to get up to speed with what they were doing. The best way to keep things moving along is to have multiple people who have actual experience in each part of the code. Collective code ownership ensures that people work with different parts of the code as needed and that they don&#8217;t get blocked when they need to accomplish something.

Which brings me back around to pairing. Pair programming eliminates the need for code reviews, since every line of code has two people looking at it from early on. I find code reviews tedious, so this is a good thing in my book. On the other hand, pairing can make it harder for individual creative output to be applied to a problem.

Pair programming gets a lot of emphasis in discussions about XP, despite being only one piece of the whole puzzle. I think that&#8217;s because it&#8217;s a huge (and unwanted) shift for many programmers. To fully utilize senior engineers in an XP environment, here is what I envision:

  * Those that are identified as senior engineers get private space and generally work that way
  * &#8220;Front-line&#8221; application developers work using the standard XP practices.
  * Collective code ownership is enforced by the project manager. The senior engineers will all be working generally in the area that is interesting to them, but their assignments in that area will change from iteration to iteration.
  * The senior engineers will pair with each other when they are starting in on a part of the code that they&#8217;re not familiar with. Once the newbie to that code is up to speed, they go back to their normal work.
  * The senior engineers will also pair with the front-line developers as needed to help out with tricky problems and ensure that the overall framework is doing what it needs to do to create the finished product.

This setup gives the best programmers the ability to exercise their creativity fully, while ensuring that business needs are met. Per XP project management practices, the senior engineers are still responsible for putting estimates on their work and being able to demonstrate progress at the end of an iteration.

Some folks may rebel against this notion of having two classes of programmers. Tough luck. It is a simple fact that not all programmers are equal, and the business should do what it can to make the best use of people. This will ultimately help the business and improve the job satisfaction of the best employees. The senior engineer differentiation also gives something for the others to aspire to, if they wish. Note that some folks who may be capable of operating as a senior engineer _prefer_ doing application development in the XP style. Those people should be rewarded appropriately as well, because they help the business meet its goals.

As everyone knows, XP is not a silver bullet. For a great many projects, it can work quite well, but ultimately most environments will need to customize XP somewhat to meet their own needs. My suggestion here is to help ensure the flow of creativity that can help boost a product from good to great, while still protecting the business from towers of knowledge.

 [1]: http://paulgraham.com/gh.html "Great Hackers"
 [2]: http://developers.slashdot.org/article.pl?sid=04/07/28/2332233&tid=156
 [3]: http://jbehave.codehaus.org/