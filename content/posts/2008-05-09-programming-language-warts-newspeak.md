---
title: 'Programming language warts: Newspeak'
author: Kevin Dangoor
type: post
date: 2008-05-09T18:49:50+00:00
url: /2008/05/09/programming-language-warts-newspeak/
aktt_tweeted:
  - 1
categories:
  - Software Development
tags:
  - newspeak

---
There&#8217;s a new language that is soon to be open sourced called [Newspeak][1]. Gilad Bracha and team are creating a new language to address what they see as the future of programming (online/offline operation, lots of service oriented design, more concurrency). They&#8217;re angling for a Smalltalk-like environment and, indeed, their current implementation is in [Squeak][2].

Ignoring that there&#8217;s at least [one other language][3] called Newspeak, it seems like Gilad Bracha&#8217;s Newspeak is built on reasonable premises. You can read a bit about [what Newspeak is like][4]. Newspeak is definitely not done yet, but things like this give me some doubt:

> note that the caret (Ë†) is used to indicate that an expression should be returned from the method, just like the return keyword in conventional languages

If I were creating a programming language, writing a sentence like that would give me pause. I would ask myself &#8220;why am I doing this differently?&#8221; If everyone in the world is using return, why choose ^? To save a few characters of typing? Really? The Newspeak document does not explain <span style="font-style: italic;">why</span> it&#8217;s like that, it just states matter-of-factly that ^ means return.

Though they reference Self as an influence for Newspeak, they chose to go with classes rather than prototypes. That&#8217;s a good decision for adoption, because people are familiar with and like classes.

Anyhow, I think Newspeak looks interesting and it will be interesting to see how it matures. But too many arbitrary changes from &#8220;conventional&#8221; syntax are likely to hinder adoption.

 [1]: http://bracha.org/Site/Newspeak.html
 [2]: http://squeak.org/
 [3]: http://www.penjili.org/newspeak.html
 [4]: http://bracha.org/newspeak.pdf