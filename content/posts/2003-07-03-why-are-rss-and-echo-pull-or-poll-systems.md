---
title: Why are RSS and Echo pull (or poll) systems?
author: Kevin Dangoor
type: post
date: 2003-07-03T22:04:23+00:00
url: /2003/07/03/why-are-rss-and-echo-pull-or-poll-systems/
categories:
  - Features
  - Software Development

---
There has been huge discussion about [Echo][1], the in-progress replacement for RSS and the Blogger API. I agree that the notion of coming up with a new, clean, unambiguous syntax can help the state of blog reading and production tools. Something that has bothered me for some time, however, is the question of &#8220;why are RSS feeds provided on a pull basis?&#8221;
  
<!--more-->


  
RSS readers are constantly connecting to web servers and checking for changed files. Let&#8217;s say I add a blog entry once per day. It would not be uncommon for people to issue requests every 3 hours. I would probably get 3 requests from them over the course of a working day, despite the fact that I only make one new post. Plus, their RSS reader is potentially polling dozens of blogs every three hours. Gadzooks! What a waste of bandwidth! Sure, modern tools don&#8217;t download the whole RSS file if there haven&#8217;t been any changes, but that&#8217;s still a whole bunch more requests than is needed. It&#8217;s to the point where Slashdot has to put limitations on feed readers.

And it isn&#8217;t even the best for the user experience. If I update my blog right after the user has polled my RSS feed, they&#8217;ll be waiting 3 hours before they actually see that post.

This is really begging to be a &#8220;push&#8221; application! A new entry in an RSS feed is essentially a broadcast event. The reason that this is not a push application is that creating a push application is hard! Some large portion of internet users are behind firewalls and their computers can&#8217;t be contacted directly to push a notice out to them. So, we end up with this very wasteful system.

But, that needn&#8217;t be the case and the solutions do not have to conflict with what&#8217;s going on with Echo. Here are some ways around the problem:

### Aggregators

This model is not entirely unlike Usenet. A single server collects up the RSS or Echo feeds and gets polled periodically by clients.

**Pros**: Doesn&#8217;t really change any existing tools.
  
**Cons**: Who&#8217;s going to run the aggregator? ISPs are basically the only ones that would benefit from this because of the reduced bandwidth usage. But would they really provide a comprehensive aggregator for their customers, picking up any feed that a customer wants? Have any ISPs even considered this?

### Email

We&#8217;ve all got programs polling our email servers already, and email already follows the push paradigm. In fact, many RSS feed readers have copped the common 3 pane look of an email program. Wouldn&#8217;t it have been better just to integrate with the email program, rather than writing a whole new one?

Why can&#8217;t we send new entries in email with an Echo attachment?

**Pros**: Everyone has an email server, so there is no need for new servers to be deployed. Email protocols are well-understood.
  
**Cons**: The email protocol is not particularly high-speed. It would probably take Slashdot a fair bit of time to send out 200,000 email messages every time a post goes up. Support would need to be added to email programs for Echo messages (or people would need a separate program that polls their email for Echo messages).

### IM

An instant message could be sent for each new entry, and a feed reading system could store and display the messages in ways that are similar to what we see today.

**Pros**: Protocols are already designed to handle small bits of information being sent around.
  
**Cons**: Hooking up weblog tools to an IM system is more difficult than generating an RSS or Echo file. Supporting all of the popular IM systems may be nontrivial (AOL, ICQ, MSN, Y!), even if Jabber provides gateways. (Would every blog have the access to broadcast out a bunch of Jabber message with each new post?)

## Further reading

I am by no means the first person to think that the current way these tools work is crazy.

  * Dan (Squawks of the Parrot) [imagines using a Usenet news sort of system][2] to send change notifications. There&#8217;s some interesting discussion on the site as well.
  * Colin Stewart proposes [a system where servers subscribe for notifications, which then get distributed to clients][3]. This is similar to the aggregation model above, except that the aggregator gets change notifications pushed to it, instead of polling for them.
  * Mark Pilgrim talks about the problem (with copious links) in [Push by any other name][4], comparing RSS (rightly so) with PointCast. PointCast essentially followed the aggregator model, but it came around at a time before you could get feeds from specific people.
  * garym on Advogato talks about sending [RSS via NNTP][5] (not just Usenet-like, but actually Usenet protocol!)
  * Brad Wilson also fired up some discussion about the [issue of bandwidth][6].

I&#8217;m sure that there have been many, many more commentaries on this subject. Perhaps no one has really taken this problem and run with it because there wasn&#8217;t compelling enough money in it, or because they would have to work with other people (like email-client people).

## Conclusion

People have already done experiments in all of these areas. What&#8217;s really needed is tool support.

At the time that Pyra introduced the Blogger API, the notion of using any tool other than the weblog software you&#8217;ve got to post to your blog was nonexistent. Since then, a whole bunch of tools have risen up that allow you to post to your weblog.

Similarly, if we see a major blogging tool and feed aggregator start sporting easy-to-use subscription broadcast systems, other tools will follow suit and we can be free of the RSS bandwidth black hole.

 [1]: http://www.intertwingly.net/wiki/pie/RoadMap "RoadMap - Sam Ruby's Wiki"
 [2]: http://www.sidhe.org/~dan/blog/archives/000159.html
 [3]: http://www.owlfish.com/thoughts/cnws-2003-04-08.html
 [4]: http://diveintomark.org/archives/2002/10/21/push_by_any_other_name.html
 [5]: http://www.advogato.org/article/651.html
 [6]: http://dotnetguy.techieswithcats.com/archives/003194.shtml