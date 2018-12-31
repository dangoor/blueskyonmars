---
title: Firefox Developer Tools Input Summary Jan 26
author: Kevin Dangoor
type: post
date: 2012-01-26T14:19:44+00:00
url: /2012/01/26/firefox-developer-tools-input-summary-jan-26/
categories:
  - Mozilla

---
## Lots of Feedback {#lots_of_feedback}

[Firefox Aurora][1] has a fairly small audience, but it represents a good time to start collecting feedback on new features. [Firefox Beta][2] has a much larger audience. Both Aurora and Beta have a handy &#8220;Feedback&#8221; button in the toolbar, and I thought that now was a good time to dive into that feedback since we&#8217;re reaching the end of the Firefox 10 beta cycle. Firefox 10 is a big deal, because it adds the Page Inspector and related tools for web developers.

In this post, I&#8217;m focused on the input that we&#8217;ve received from the Feedback button. We get input from many other sources as well:

  1. user studies
  2. blog comments
  3. Twitter/G+/Facebook (mostly Twitter)
  4. Google Alerts (blog postings, press articles)
  5. [Bugzilla][3]
  6. [dev-apps-firefox][4]
  7. irc.mozilla.org #devtools
  8. surveys
  9. and, of course, the Feedback button input from Aurora and Beta users

I&#8217;m probably forgetting some input channels.

Those of us working on Firefox developer tools have ideas of what we (as developers ourselves) would like to see in the tools. Hearing from other web developers goes a long way toward making sure that we&#8217;re doing the right things to make tools that work well for many people.

Keep the input coming!

## Summary of Input {#summary_of_input}

The entries from the Firefox Feedback button are collected and searchable at [input.mozilla.com][5]. I went through the input for a variety of searches going back to mid-December to get an idea of what the sentiment was like.

During that time, I counted <span style="color: green">63 positive</span> feedback entries for our new built-in tools and <span style="color:red">22 negative</span> entries. That&#8217;s 74% positive. Across Firefox as a whole, most people (between 55-65% over the past month) who hit the Feedback button did so because they found some aspect of Firefox they didn&#8217;t like. People are going out of their way to say that they like the new tools, and that&#8217;s fantastic.

Firebug has its own [feedback channels (a mailing list, bug tracker, etc.)][6], but we get some input about Firebug via the feedback button. I saw <span style="color: green">36 positive</span> and <span style="color: red">22 negative</span> entries, which is a 62% positive rate. Again, this rate is much better than the overall and the sentiment that I&#8217;ve seen toward Firebug in other channels has been super positive.

More interesting information comes up when you look at some of the specific feedback&#8230;

## Recurring comments about Firebug {#recurring_comments_about_firebug}

Of the 22 negative comments about Firebug, 10 were about Firebug crashing, or the browser crashing in conjunction with Firebug. People working on Firefox and Firebug take crashes seriously, so I hope that people file bug reports or ask for help for these kinds of problems. It turns out that there is a known crashing problem that is fixed in Firefox 10 (due on Tuesday). Let&#8217;s see how these numbers shift after 10 is released.

Five comments about Firebug reported a problem getting Firebug to run on the user&#8217;s version of Firefox. I find this a bit unexpected, because Firebug has broad compatibility these days. See the listing at the top of this [blog post about Firebug 1.9][7]. If I had to guess, I&#8217;d say that this problem is because some people did not get their copy of Firebug from addons.mozilla.org. Hopefully, the number of people getting Firebug elsewhere (getfirebug.com) has been dropping. Firefox Nightly users need to get Firebug from getfirebug.com, but those of us running Nightly generally know the risks we&#8217;re taking, right?

All of that said, the majority of comments about Firebug were along the lines of &#8220;I love Firefox because of Firebug&#8221;. Some of them were marked as praise with the simple comment &#8220;Firebug&#8221;.

## Recurring comments about the Firefox Developer Tools {#recurring_comments_about_the_firefox_developer_tools}

Three people stated that the tools should live in add-ons because the user is concerned about memory bloat and speed. On this point, it&#8217;s worth noting that every commit to the mozilla-central repository (from which Firefox is built) is checked for memory usage and speed. The tools we&#8217;re adding to Firefox do not negatively impact Firefox&#8217;s memory use and speed.

On the flip side, six people stated that they like having the tools built-in.

Three people said that they don&#8217;t think we should be duplicating Firebug. [I&#8217;ve written about this already][8], so I wont rehash it here.

Four people want a &#8220;layout view&#8221; that shows margins, padding, etc. for an element. Those people are in luck! We&#8217;ve got a [patch in progress][9].

Quotes like &#8220;THE NEW DEVELOPER ELEMENT INSPECTOR IS SO SLICK!!!&#8221; and &#8220;3d Web Developer Layering. (Ctrl + Shift + I) This is _SO_ helpful!&#8221; reflect a lot of the sentiment in the positive feedback.

## Thanks, and I&#8217;m looking forward to more! {#thanks_and_i8217m_looking_forward_to_more}

The release of Firefox 10 and new notices for Aurora and Beta users will likely net us more feedback in the coming weeks. We&#8217;ll be listening!

I&#8217;ll close with this tweet from Brian Blakely:

> [&#8220;Perhaps the next-generation webdev IDE will be a browser. Somewhat related, FF&#8217;s dev tools are really coming along&#8221;][10]

 [1]: http://mozilla.org/aurora
 [2]: http://mozilla.org/beta
 [3]: https://bugzilla.mozilla.org/buglist.cgi?quicksearch=comp%3A%22Developer%20Tools%22%20&list_id=2148767
 [4]: https://lists.mozilla.org/listinfo/dev-apps-firefox
 [5]: http://input.mozilla.com/
 [6]: http://getfirebug.com/community
 [7]: http://hacks.mozilla.org/2012/01/firebug-1-9-new-features/
 [8]: http://blog.mozilla.com/devtools/2011/05/25/the-relationship-between-firebug-and-mozilla-developer-tools/
 [9]: https://bugzilla.mozilla.org/show_bug.cgi?id=683954
 [10]: https://twitter.com/#!/brianblakely/status/162016048336478208