---
title: My onboarding experience at Khan Academy
author: Kevin Dangoor
type: post
date: 2015-05-29T14:27:46+00:00
url: /2015/05/29/my-onboarding-experience-at-khan-academy/
categories:
  - Software Development

---
I’m in my third week at [Khan Academy][1] and thought I’d write a little about my experience with the onboarding process here. I’m a remote employee and my first two weeks have been here at home, 2,000+ miles away from most of my coworkers. This means that I don’t have the benefit of in-office osmosis of thought or lunchtime talk with the others. My quick summary is that onboarding at Khan Academy works very well indeed.

The starting point is a welcome email that arrives _before_ your first day. This email provided me with a bunch of background even before I started. Part of that includes this Trello board:

<blockquote class="twitter-tweet" lang="en">
  <p lang="en" dir="ltr">
    Our new <a href="https://twitter.com/trello">@trello</a> board for onboarding KA folks courtesy of <a href="https://twitter.com/kayla_bills">@kayla_bills</a> and @KarinaMurtagh and my dog Fleetwood <a href="http://t.co/k5e22H4QGz">pic.twitter.com/k5e22H4QGz</a>
  </p>
  
  <p>
    &mdash; Ben Kamens (@kamens) <a href="https://twitter.com/kamens/status/483701926874189825">June 30, 2014</a>
  </p>
</blockquote>



This is the first time I’ve seen Trello used as a documentation format, but it works nicely in this instance. You work your way across the Trello board to:

  * get your paperwork in order
  * get everything you need to work productively
  * learn about company culture

The company culture information was especially good because it gave me a lens through which to look at everything I was seeing. Everything from Khan Academy&#8217;s mission (free, world-class education for anyone, anywhere) to our development core principles (&#8220;shipping beats perfection&#8221; and others) to the very deep way in which career development is approached is covered on the culture pages. This both sets expectations for me _and_ helps me have a mindset to keep this wonderful culture going.

From there, I spent a good deal of time reading Google docs and our documentation site. Khan Academy’s documentation is great, covering from the highest level strategies down to details on our day-to-day development processes. One part of KA’s culture is that “everyone can fix everything”, so there was little about the documentation that was stale or out of date.

Alan Pierce ran a “dev crash course” that was recorded and that helped, but I do think a bit more documentation at the 10,000 foot level (what are the pieces and how do they fit together?) would help. I have some ideas in mind for that and hope to have something together soon.

## Not getting lost and keeping in touch

I’ve been working with a couple of mentors (James Irwin and [John Resig][2]) since I started. Their help has been invaluable because any documentation will have _some_ holes. I’ve also found it easy to get in touch with the right people by using `git blame` as I’m working on a piece of code. Going through code reviews and talking with the other developers has been very helpful in learning how things work, why they work as they do and some areas we might want to improve going forward.

We make heavy use of [HipChat][3] at Khan Academy. This is one thing that definitely makes me feel like a part of the team and less distant from everyone in California. [Radical email transparency][4] helps with shared context as well. I’ve been delighted at the quite reasonable pace of email so far, and I think that’s largely due to the split between HipChat and email. That’s something that many organizations seem to be finding as they adopt Slack, which is quite similar to HipChat.

We have meetings via [Fuze][5] or Google Hangouts. Video conferencing just gets better over time.

## Developer Setup

As a developer with a new machine, you start by grabbing the khan-dotfiles project and running `make` in there. khan-dotfiles is nice because it gives you everything you need and if the requirements change, you just update the project and re-run `make`.

Re-running the khan-dotfiles setup is likely much more common than starting up a fresh machine, so it&#8217;s not entirely suprising that I ran into a problem setting up my brand new machine. One of the first bits of code I submitted was a fix for khan-dotfiles.

We use [Phabricator][6] and the workflow is quite different from the GitHub flow that I’m used to from day-to-day work on [Brackets][7]. Again, though, good docs save the day.

Or, I should say, good docs, tools and chats with coworkers save the day!

## Support

Khan Academy recently started a support rotation. Every three weeks, a different set of developers will take on support duties, responding to problems that people have filed. Having a set of developers designated (for a time) to work on support is good because it enables everyone else to focus on their project work rather than context switching between bugs and progress work. It also gives everyone a chance to see what people are encountering on the site and an opportunity to step out of their comfort areas in the code and into some other parts.

Newbies like me start out on support, which has worked out well because I have gotten to dig in to a few different areas of the code so far. The fixes I’ve made so far have not required me to change much code, but I have been reading quite a bit of code and learning different parts of the process and tooling along the way.

## Elements of good remote developer onboarding

Though I still have a lot to learn (there&#8217;s a lot of code there!), Khan Academy&#8217;s onboarding process has worked well in getting me up and running. My summary of the key elements:

  * An overall welcoming attitude (seriously, _everyone_ has been great!)
  * An assigned mentor that can handle all of the random questions that come up
  * Documentation of culture, tools, processes
  * Communications channels that work across time and space (HipChat/Slack, email with archives, video conferences with recordings)

It turns out that many of the elements that make an environment remote worker-friendly _also_ make onboarding easier. In fact, this list of items would seem to be very similar to the techniques used in some large and successful open source projects. That&#8217;s probably not a coincidence.

 [1]: http://khanacademy.org
 [2]: https://twitter.com/jeresig
 [3]: https://www.hipchat.com/
 [4]: http://bjk5.com/post/71887196490/email-transparency-at-khan-academy
 [5]: http://fuze.com
 [6]: http://phabricator.org/
 [7]: http://brackets.io