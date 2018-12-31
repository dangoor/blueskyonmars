---
title: Putting a hosting company to the test
author: Kevin Dangoor
type: post
date: 2005-09-20T02:54:57+00:00
url: /2005/09/19/putting-a-hosting-company-to-the-test/
categories:
  - Software Business
  - TurboGears

---
Pricing is an interesting thing. As a general rule, unless you&#8217;re in a completely commodity business, price is not related to the cost of something. Price is based on the _value_ of something and what people will pay. What this means is that the cost structure of a product or service is not necessarily in line with the price.

What does that have to do with hosting? Well, hosting companies typically charge for packages based on how much data you transfer in a month. However, the way they pay for bandwidth is not based on how much is transferred per month, but rather how much capacity they have for instantaneous transfer.

So, let&#8217;s say I have a 2,000GB per month allotment. And then I put an 80MB file online that gets downloaded 1,800 times in a couple of days. From my perspective, I&#8217;ve only used 144GB of my quota and have plenty of room to spare. My hosting company, however, looks at the fact that I was, at times, using almost all of their 100Mbit/second connection to the Net.

So, what happens? They disconnected my server. Their original rationale for doing so was a reasonable one: my traffic had spiked so much over the previous 5 months of traffic statistics that they thought I had been hit by a worm. Of course, when I told them that my server was just really popular right now, they brought up the fact that my bandwidth usage was harming connectivity for other customers.

One option was mod_throttle to prevent the &#8220;20 Minute Wiki&#8221; screencast from using too much bandwidth. That&#8217;s not a good option, though, because I \*want\* people to have a good experience downloading things.

Another option was to switch to a larger hosting company that has plenty of capacity to deal with the good times when they occur. That&#8217;s the route I&#8217;m taking, though it meant taking the screencast down just when there were lots of people watching.

[TurboGears.org][1] was completely unavailable from about 12:25 to 1:10 today. From 1:10 to 3:45, the site was up but the screencast was down.

[Bob Ippolito][2] put up a mirror at MochiKit.com, which brought the screencast back online. Bob has served up about 225 views already. [Scott Oertel][3] also offered to mirror the file. And, impressively enough, I got email a short time ago that my new Go Daddy server is up. So, the bandwidth issue has been dealt with&#8230;

When you sign up for a hosting plan, keep the difference between price and cost structure in mind. A small hosting company doesn&#8217;t have the instantaneous bandwidth to deal with something that&#8217;s very popular, even if your plan calls for &#8220;uncapped&#8221; bandwidth and huge data transfer limits.

**Update:** I didn&#8217;t mean for this to sound so negative toward my hosting company. My philosophy in business is that every deal should be a win/win, and it&#8217;s not about squeezing the last dime out of the other party. I completely understand that one customer spending $99 a month on hosting is not a good tradeoff against all of your other customers.

I&#8217;ll be spending 60% more at Go Daddy, but I also have the confidence that my server is not going to overrun their network. I also get some other services that are simply not available to a small outfit like the one I&#8217;ve been with. I haven&#8217;t been mentioning them by name, because I have no ill will at all toward them and don&#8217;t want to dissuade people from using them, since their service will likely suit some people just fine.

I&#8217;ve also been getting more interesting email regarding this topic, so I may have a little more to write on the hosting picture later today.

 [1]: http://www.turbogears.org
 [2]: http://bob.pythonmac.org/
 [3]: http://www.gawr.com