---
title: 'The Tale of the Merry Squid: Teaching Programming with Minecraft'
author: Kevin Dangoor
type: post
date: 2015-05-19T13:55:24+00:00
url: /2015/05/19/the-tale-of-the-merry-squid-teaching-programming-with-minecraft/
categories:
  - JavaScript
  - Software Development

---
<img src="http://www.blueskyonmars.com/images/2015/05/The-Merry-Squid.png" alt="The Merry Squid" width="161" height="204" class="aligncenter size-full wp-image-3109" />

This past January and February, I taught a class that introduces children to programming through Minecraft. I called the class &#8220;The Merry Squid&#8221;, and this is my story of how it went. For the benefit of those who don&#8217;t want to read the whole thing, I&#8217;ll note up front that [the class is available online][1].

## Programming in Minecraft

There are so many things that I think are great about Minecraft. Since it&#8217;s written in Java, people could use a bit of perseverance (okay, a _lot_) to figure out how to hook in to Minecraft&#8217;s normal operation and change it. If you&#8217;ve played Minecraft, you&#8217;ve probably already heard about &#8220;mods&#8221; that do this.

One Minecraft mod is called [ScriptCraft][2]. ScriptCraft is a mod that lets you write mods, _in JavaScript_. Even better, it lets you run bits of JavaScript code from within Minecraft itself.

Minecraft is set up for multiplayer games, so there’s both the client part that runs the graphics and the server part which keeps track of the state of everything in the world. ScriptCraft is a server mod, so that means you can only change things that affect the state of the world and not the graphics that appear on screen. There’s an awful lot you can do within those boundaries, though!

Possibly the best thing about Minecraft for teaching programming is that many kids _love_ it. There’s a strong built-in motivation for them to try things out and see what they can create.

## From Logo to Minecraft

[Logo][3] was possibly the first &#8220;teaching&#8221; language that was geared toward kids. Using simple commands, children could draw pictures by moving a &#8220;turtle&#8221; around on the screen or even an actual physical robot on a piece of paper.

ScriptCraft includes a JavaScript object called &#8220;the Drone&#8221; that feels a bit like the turtle from Logo. Using functions on the Drone, you can &#8220;draw&#8221; with Minecraft blocks. Want to make a 10x10x10 cube? Normally, that would mean placing 1,000 blocks, one at a time. Using the `/js` command provided by ScriptCraft turns that into just a quick bit of typing.

That instant feedback of typing a command and immediately seeing the result in your Minecraft world is fantastic. This seemed like the perfect entry point for getting children to do some JavaScript.

## Setup Pain

As easy as it was to start coding with ScriptCraft, getting ScriptCraft itself running was not easy for many.

Most of the parents of the children in my class are not “computer people”. I created step-by-step instructions to set up Minecraft with the required mods on both Windows and Mac, but setup was still not easy. An automated installer would have been nice, but I didn’t have time to build one.

To make matters more challenging, the class met in a building that has barely functional Internet access. USB flash drives are not quite a thing of the past yet.

Also, some of the computers launched programs very slowly. I didn’t have time to track those problems down either, because I had a class full of kids, so my focus was on making sure that everything _could_ run, even if launching was slow.

It’s worth noting that Minecraft is a fairly resource intensive program. That’s probably why Minecraft Pocket Edition was a ground up rewrite in C++: desktop Minecraft takes a pretty beefy computer to run acceptably.

Other local people who teach Minecraft classes bring their own equipment and teach with [Minecraft: Pi Edition][4]. This certainly gets rid of the setup pain, but the Pi Edition is nowhere near as interesting as the things you can do with ScriptCraft.

[LearnToMod][5] launched just as my class was starting. It sounds like they run the server for you which certainly makes life easier for the participants.

## Graduating to code in files

There’s a limit to how much you can do from Minecraft’s little command line. It’s like writing programs in tweets. To do anything really cool, you need to edit JavaScript code in files.

The experience of modding Minecraft with JavaScript is still pretty great. You don’t quite have the immediacy of entering code in the command line, but you can dynamically reload your code without having to restart Minecraft. The iteration loops are still quick.

I got everyone set up with [Brackets][6] because I knew the editor well and I knew that the out-of-the-box JavaScript listing would come in handy.

Everyone was successful in running the new scripts that I provided each week. Sometimes they made their own customizations to the scripts, and some of the children clearly were writing some code of their own with varying degrees of success.

## My “flipped classroom” experience

I taught this class as a “flipped” class: I’d post a video each week which provided the new material to learn and then planned for us to do more together during class time. My thinking with this was that by doing the experimentation at home after watching the videos, the kids could spend as much time as they wanted playing around with it.

When class times came around, I found that sometimes I needed to do a fair bit of tech support and that the environment hadn’t quite encouraged the kids to work together on things. There was a bit of “hey! look what I did!” that happened, but not quite as much as I’d have liked.

My [Egg Hunt mini game][7] from the last session was ridiculously complicated, but I think it did serve well to show off what was possible and was a fun activity that we all did together on the last day in class.

The flipped classroom approach is great because I could put the class online once it was done. At least one parent and child have taken a look and found it helpful:

<blockquote class="twitter-tweet" data-conversation="none" lang="en">
  <p lang="en" dir="ltr">
    <a href="https://twitter.com/walter">@walter</a> <a href="https://twitter.com/dangoor">@dangoor</a> my son is having fun with the drone while going through Kevin's videos, so thank you both! <a href="http://t.co/wVwxJ5ESVn">pic.twitter.com/wVwxJ5ESVn</a>
  </p>
  
  <p>
    &mdash; Donncha Ó Caoimh (@donncha) <a href="https://twitter.com/donncha/status/587273519672778753">April 12, 2015</a>
  </p>
</blockquote>



## Fun was had by all!

These children were already fans of Minecraft, but were entirely new to writing code. I tried to balance doing fun things with Minecraft that they couldn’t have done before with learning some JavaScript, putting the greater emphasis on fun-with-Minecraft than learning-JavaScript.

Despite the challenges that I’ve mentioned here, I had a good time creating and running the class and the impression that I got from the kids was that they enjoyed taking the class.

## What did I learn?

I learned as much as the children did through this experience.

  * The ScriptCraft drone with the in-game REPL is brilliant. Kids love it and can make good use of it.
  * LearnToMod sounds awesome. Their approach (run the servers on behalf of the learners) makes a whole lot of sense. Alas, with the poor Internet access we had, doing the class in conjunction with LearnToMod would not have been an option.
  * The creator of ScriptCraft has since published a book ([A Beginner’s Guide to Writing Minecraft Plugins in JavaScript][8]). Teaching a class based on pre-existing material like that could have made my life easier.
  * I shouldn’t sign up to do a class when I’m already oversubscribed. At the time that I started exploring the class, I _thought_ there would be no trouble… but I had so much going on when the class started that it was a struggle to sneak in my work for the class. The timing was just not quite ideal.
  * Even though the flipped classroom approach wasn’t as smooth as I hoped, I would definitely do that again. Especially when it comes to homeschooled kids, it makes sense for the kids to spend as much time exploring as they want. I would want to make sure that the in-class activity time could be smoother than the way it went for this class.

Minecraft is used for [teaching a wide variety of things][9], and ScriptCraft offers a lot for people who want to learn programming in Minecraft, once you get past the setup.

 [1]: http://kevindangoor.com/merrysquid/
 [2]: http://ScriptCraft.org
 [3]: https://en.wikipedia.org/wiki/Logo_%28programming_language%29
 [4]: http://pi.minecraft.net/
 [5]: http://www.learntomod.com/
 [6]: http://brackets.io
 [7]: http://www.kevindangoor.com/merrysquid/part8/
 [8]: http://www.peachpit.com/store/beginners-guide-to-writing-minecraft-plugins-in-javascript-9780133962574
 [9]: http://minecraftedu.com/