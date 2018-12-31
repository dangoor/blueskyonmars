---
title: Don’t let support do you in!
author: Kevin Dangoor
type: post
date: 2005-01-23T00:27:37+00:00
url: /2005/01/22/dont-let-support-do-you-in/
categories:
  - Software Business

---
What do you think about first when thinking about starting a new small software shop? If you&#8217;re like me, you think about the product first. You think about the cool idea and some of the nifty bells and whistles. You think about some interesting parts of the implementation. That&#8217;s all well and good, because a great software company needs to start with a good product. But, when you&#8217;re starting your own small software shop, there are two things that will end up being more important to your success: marketing and support. In this article, I&#8217;m going to write a bit about surviving your business&#8217; support needs.

Time and money are both hugely constrained in your typical, home-grown business. (If you&#8217;re working with venture capital, go ahead and hire that team of support staff 🙂 When you&#8217;ve got only a small handful of people working with you, you need to optimize on time and money outlay. Each email or phone support request is going to take time, so you need to do what you can to avoid as many as possible.

## Work on usability

I can&#8217;t afford a full-blown usability study of my application. What I can do, and I&#8217;m sure you can to, is find someone who fits a reasonable user profile for your application and just observe them using the software. Start them out from the very beginning (your website), and see how they do with downloading and installing the software. Then, watch how they actually use the software.

Are there things they did frequently that required more clicks than they should have? Was there something that they wanted to do, but got lost while doing it? For each time they turn to you either for reassurance or to ask a question, that could be a sign of support requests to come. Except those support requests could come from hundreds of customers all over the world, rather than just one person sitting in front of you.

Anything you can do to watch real people using your software (without assistance) will give you insight into making your software better. [Usability Testing in Practice][1] by Andrew Starling gives a quick overview of how the pros do it. [Observing the User Experience: A Practitioner&#8217;s Guide to User Research (Morgan Kaufmann Series in Interactive Technologies)][2] by Mike Kuniavsky may provide some good tips (I haven&#8217;t read it, but it appears to be one of Amazon&#8217;s higher sellers and has four 5-star reviews).

## Do sufficient testing

In the days of yesteryear (say 5 years back), it used to be the case the a QA group was responsible for all of the testing. A developer would write some code, fire up the program, test that one thing and proclaim it &#8220;done&#8221;. Well, it&#8217;s no longer yesteryear, and my tiny company doesn&#8217;t have a QA department.

From time to time, I see people write that &#8220;unit testing is not a silver bullet&#8221;. That&#8217;s true, but that doesn&#8217;t mean you shouldn&#8217;t do it. Test driven development can improve your designs and improve your ability to fix bugs quickly. If you want to have a low bug count on release, do your automated tests.

Since I don&#8217;t have a QA department, I need to have a good beta test program. In fact, I need a good _alpha_ test program. The earlier in the process that you have more people involved, the fewer gotchas you&#8217;ll have later. Try to get people with different experience levels and computer setups so that you&#8217;ll catch more problems before release. All of the really weird stuff is going to come out of the woodwork after release, so you might as well get the easy ones out of the way earlier.

Public betas can be a double-edged sword. While they do allow you to get the broadest possible exposure and shake out more bugs, you may also attract some people who have release-software expectations for your beta and others who would just give up rather than reporting bugs. For a beta test to be useful, the testers need to know that the software is almost, but not quite, done and that you&#8217;re counting on them to provide bug reports.

One option to consider is to do private beta testing, but take your first &#8220;release candidate&#8221; and put it out there as a public beta. A release candidate is not like a traditional beta. With an RC, you believe that the software is ready to ship. By putting it out there as a public beta, that gives you a chance to broaden your testing exposure while still giving some of the impression that it&#8217;s not fully done. Once you&#8217;ve seen the response from the RC, then you know you&#8217;re safe to release.

## Make sure the answers are there and accessible

Your website needs a search engine. It doesn&#8217;t matter how you do it (you can even use Google, if you wish), but just make sure that people can search. And people really need to be able to search _the whole site_ in one go. If your site is a patchwork of HTML files, PHP forums and a Movable Type blog, you have an interesting integration problem (go with Google and save yourself the headache).

My plan for that, by the way, is to use [Drupal][3] for my site. Something like [Plone][4] is also a good choice. Both of these let you incorporate a variety of content with discussions and more, all of it under one always-up-to-date search engine. They&#8217;re also both free.

With a bit of clever packaging, you should be able to provide a lot of the same content in multiple forms: a manual, context-sensitive help, and a frequently asked questions list. Especially in this age of hyperlinks, many FAQs can be answered with a short response and a link to the appropriate part of the documentation. All of this content should be on your website.

If you write all of your docs in some kind of structured text format (HTML, XML, ReStructured Text) and you&#8217;re handy with a language like Perl, Python or Ruby, you should be able to put your content to work in many ways.

If you can afford one (which I can&#8217;t right now), hiring a professional documentation writer can be a very valuable thing. I can write reasonably well, but I know that a pro would be able to do the job more efficiently and will avoid common pitfalls.

## Only answer a question once

While I&#8217;m writing about trying to save support costs, the idea is not to save the costs at the expense of providing good support. Word of mouth can be crucial to a small business, and there&#8217;s no better way to spoil it than bad support. So, the goal is to help the customers help themselves as much as possible, and then to respond quickly to anything that wasn&#8217;t caught by those efforts.

A web-based forum can be a powerful tool. Any questions that get asked there automatically become searchable. When you post an answer, you&#8217;ve automatically increased the chance that the next person who has that same question may find the answer in a search. If a question pops up more than once, or seems like something important, it definitely pays to get that into your main documentation right away.

The thing to keep in mind about a forum is that it&#8217;s _public_. If you try to squelch criticisms of your product, they _will_ come back to bite you. It certainly pays to remove outright offensive forum postings. But, genuine criticisms, even if you disagree with them, should be taken seriously and responded to. As long as you handle things reasonably, your other customers will still see you as being responsive.

## Some parting thoughts&#8230;

I&#8217;ve provided support in a variety of capacities for different kinds of products over the course of my career. The capabilities of modern computers and the internet have _potentially_ greatly reduced the support burden of creating a software product. To get the benefit, though, you need to plan ahead and take advantage of the tools and techniques available today. The tools are free, you just need to put in the time. The more customers you end up with, the better leverage you get out of that time spent up front.

 [1]: http://wdvl.internet.com/Authoring/Design/UsabilityTesting/
 [2]: http://www.amazon.com/exec/obidos/ASIN/1558609237/blueskyonmars-20
 [3]: http://www.drupal.org
 [4]: http://www.plone.org