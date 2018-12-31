---
title: Introducing the Web Console
author: Kevin Dangoor
type: post
date: 2010-09-01T13:28:56+00:00
url: /2010/09/01/introducing-the-web-console/
categories:
  - Mozilla
tags:
  - devtools
  - firefox

---
David Dahl has been leading the work on Firefox 4&#8217;s Web Console feature and has blogged about the work along the way. Over the past month, we&#8217;ve landed a whole bunch of improvements to the Web Console in Firefox 4 Beta, and I wanted to give my take on what the Web Console has to offer for web developers.

## What _is_ the Web Console?

I first learned to program a computer in BASIC on a TRS-80 Model III. I&#8217;m dating myself there, but oh well. Believe it or not, my first programs didn&#8217;t always work the way I intended them to and, surprisingly enough, they still don&#8217;t. I had two main tools to help me figure out what was going on: a [&#8220;read eval print loop&#8221;][1] (REPL) and &#8220;print&#8221;. Using the REPL, I could type in simple statements and get immediate results, as a way of testing that how I think an individual operation should work is actually how it does work. Using &#8220;print&#8221;, I could have my program display certain values along the way so that I could make sure that they met my expectations while the program was running.

Even today, REPL and print continue to be two simple and fundamental tools for learning how a system works and troubleshooting problems. The Web Console gives you these two features for web pages that appear in Firefox.<figure id="attachment_2757" style="width: 473px" class="wp-caption aligncenter">

[<img class="size-full wp-image-2757 " title="WebConsoleOverReddit" src="http://www.blueskyonmars.com/images/2010/08/WebConsoleOverReddit.png" alt="" width="473" height="160" srcset="https://www.blueskyonmars.com/images/2010/08/WebConsoleOverReddit.png 789w, https://www.blueskyonmars.com/images/2010/08/WebConsoleOverReddit-300x101.png 300w" sizes="(max-width: 473px) 100vw, 473px" />][2]<figcaption class="wp-caption-text">The Web Console atop a popular website</figcaption></figure> 

You can see the Web Console for yourself today by downloading the [Firefox 4 beta][3].

## The Log

When you open the Web Console from Firefox&#8217;s Tools menu (or using the ctrl-shift-K/cmd-shift-K keyboard shortcut), you&#8217;ll see a panel drop down from the top of the content area of the browser. In the current Firefox 4 beta release, the panel is empty when it first opens, but the Firefox 4 final release will collect up logging messages even while the console is closed.

If you open the Web Console and then go to a page, you&#8217;ll see a whole bunch of output. Typically, there will be many &#8220;Network&#8221; requests listed. Sometimes, you&#8217;ll see CSS or JavaScript errors displayed. It doesn&#8217;t take long for that output to quickly become overwhelming, so we&#8217;ve got a simple solution in place to deal with that: filtering. Just above the log output area, there are a number of controls that you can use to pare down the output and see just what you need to see.

  * The Net, CSS and JS controls determine which of those types of messages from the browser should appear in the output.
  * The Errors, Warnings, Info and Log controls determine which JavaScript-generated messages should appear in the output window (see &#8220;The console Object&#8221; below
  * Finally, there&#8217;s a search box to filter the output based on whatever you type there

Using these controls, you should be able to quickly zero in on the messages that will help you debug a problem with your page.

## Network Details

The &#8220;Network&#8221; requests that appear in the log output show you the URL to which the request was made. But what do you do if your JavaScript made a request to the right URL, but the data that came back isn&#8217;t what you expected? If you click on a network log entry in the next beta of Firefox 4, you&#8217;ll get a panel with a bunch of details about the request:<figure id="attachment_2759" style="width: 345px" class="wp-caption aligncenter">

[<img class="size-full wp-image-2759" title="NetworkPanel" src="http://www.blueskyonmars.com/images/2010/08/NetworkPanel.png" alt="" width="345" height="295" srcset="https://www.blueskyonmars.com/images/2010/08/NetworkPanel.png 345w, https://www.blueskyonmars.com/images/2010/08/NetworkPanel-300x256.png 300w" sizes="(max-width: 345px) 100vw, 345px" />][4]<figcaption class="wp-caption-text">The network request details panel.</figcaption></figure> 

With the request and response headers and body and the cookies from the request, you can dive deep into the requests made from your web pages.

## The console Object

If you&#8217;ve used the excellent [Firebug][5] extension (more on Firebug below), you&#8217;ve quite possibly encountered its &#8220;console&#8221; object that is available to JavaScript. console provides a number of useful methods, including a set used for logging information: log, info, warn, error. All four methods work the same way and represent different levels of information logged from log as the lowest level to error as the highest. You can pass in multiple arguments and they will have their string representations glued together for the output. For example, if the variable food is &#8220;avocado&#8221;, then console.log(&#8220;My favorite food is&#8221;, food, &#8220;and its info is&#8221;, anObject) will output &#8220;My favorite food is avocado and its info is [object Object]&#8221;.

By strategically using the different logging levels, you can make it easy to focus on just the messages that matter to you using the filter controls.

One more note: for Firefox 4, we&#8217;re playing it conservatively with the console object. If one is already defined on the page, we won&#8217;t override it. As of this writing, there is a bug that prevents the console from working properly [on sites that define their own console object][6], but you can bet we&#8217;ll have that bug resolved soon.

## The JavaScript REPL

Read Eval Print Loops are fantastic for figuring out how a language or environment works and for testing things quickly. The Web Console features a REPL for JavaScript that gives you access to everything on your page. For every expression you type in, the Web Console will automatically output the result of that expression. That means you can use it as a simple calculator:<figure id="attachment_2756" style="width: 56px" class="wp-caption aligncenter">

[<img class="size-full wp-image-2756" title="SimpleExpression" src="http://www.blueskyonmars.com/images/2010/08/SimpleExpression.png" alt="" width="56" height="52" />][7]<figcaption class="wp-caption-text">6*7=42, but you knew that</figcaption></figure> 

For your convenience, the Web Console will automatically try to fill in variable and function names that it knows about:<figure id="attachment_2754" style="width: 194px" class="wp-caption aligncenter">

[<img class="size-full wp-image-2754" title="ConsoleCompletion" src="http://www.blueskyonmars.com/images/2010/08/ConsoleCompletion.png" alt="" width="194" height="18" />][8]<figcaption class="wp-caption-text">Automatic completion</figcaption></figure> 

By using the up and down arrow keys, you can also cycle through the history of commands that you&#8217;ve entered.

You can directly access variables that are on the page:<figure id="attachment_2753" style="width: 396px" class="wp-caption aligncenter">

[<img class="size-full wp-image-2753" title="AccessToPageVariables" src="http://www.blueskyonmars.com/images/2010/08/AccessToPageVariables.png" alt="" width="396" height="65" srcset="https://www.blueskyonmars.com/images/2010/08/AccessToPageVariables.png 396w, https://www.blueskyonmars.com/images/2010/08/AccessToPageVariables-300x49.png 300w" sizes="(max-width: 396px) 100vw, 396px" />][9]<figcaption class="wp-caption-text">Here we see that jQuery is on the Reddit home page.</figcaption></figure> 

Note that variables that you define in the Web Console are not automatically exposed to the page. If you would like to change a variable on the page, you just need to put &#8220;window.&#8221; in front of the variable name. For example, if you enter the expression &#8220;window.foo = 1&#8221;, then the variable &#8220;foo&#8221; on the page will change to 1.

With access to jQuery and knowledge that Reddit has an element on the page with an id of &#8220;header&#8221;, it becomes a simple matter to remove the header from the page we&#8217;re looking at:<figure id="attachment_2755" style="width: 781px" class="wp-caption aligncenter">

[<img class="size-full wp-image-2755" title="HidingTheHeader" src="http://www.blueskyonmars.com/images/2010/08/HidingTheHeader.png" alt="" width="781" height="107" srcset="https://www.blueskyonmars.com/images/2010/08/HidingTheHeader.png 781w, https://www.blueskyonmars.com/images/2010/08/HidingTheHeader-300x41.png 300w" sizes="(max-width: 781px) 100vw, 781px" />][10]<figcaption class="wp-caption-text">Reddit with the header hidden</figcaption></figure> 

One more note about using the REPL: if your expression returns an object, the console will just show [object Object] currently. However, you can click on [object Object] and see the object inspector:<figure id="attachment_2761" style="width: 201px" class="wp-caption aligncenter">

[<img class="size-full wp-image-2761" title="ObjectInspector" src="http://www.blueskyonmars.com/images/2010/08/ObjectInspector.png" alt="" width="201" height="419" />][11]<figcaption class="wp-caption-text">The object inspector looking at a jQuery node list</figcaption></figure> 

One nice feature of the object inspector is that it shows you a snapshot in time of the object. You can click the &#8220;Update&#8221; button if you want to see the current contents of the object.

## Firebug

The [Firebug][5] add-on has millions of users and has been making web development easier for years. If you&#8217;re one of those users, you&#8217;re probably wondering why the Web Console exists when Firebug already provides a console and much, much more. Back at the beginning of this post, I talked about how useful a REPL and print are in debugging, experimentation and learning. These things are so fundamental that we wanted them to exist in Firefox with no add-ons required.

Consider this case: you&#8217;re a web developer and you have a distant user of your application. They&#8217;re running into a problem with your app. They can tell you what&#8217;s on the screen, but they have no way of sharing a view of what the application has done to that point. If you have useful logging messages in your app, you can ask the user to copy the console output into an email message and send it to you, all without requiring them to install an add-on.

The Web Console is not a replacement for Firebug, but it will be a great tool to have in a pinch.

## What&#8217;s Next for the Web Console?

We&#8217;re still in the middle of the Firefox 4 beta test cycle, so you can expect to see additional improvements and polish as the beta progresses and we head to the release of Firefox 4. If you&#8217;d like to get involved and help make the Firefox developer tools _beyond awesome_, talk to us! Discussion about the Firefox developer tools comes on the [dev-apps-firefox mailing list/newsgroup][12] and in realtime in the #devtools channel on irc.mozilla.org. I&#8217;m also happy to receive feedback [by email][13].

 [1]: http://en.wikipedia.org/wiki/Read-eval-print_loop
 [2]: http://www.blueskyonmars.com/images/2010/08/WebConsoleOverReddit.png
 [3]: http://www.mozilla.com/firefox/all-beta.html
 [4]: http://www.blueskyonmars.com/images/2010/08/NetworkPanel.png
 [5]: http://getfirebug.com/
 [6]: https://bugzilla.mozilla.org/show_bug.cgi?id=583476
 [7]: http://www.blueskyonmars.com/images/2010/08/SimpleExpression.png
 [8]: http://www.blueskyonmars.com/images/2010/08/ConsoleCompletion.png
 [9]: http://www.blueskyonmars.com/images/2010/08/AccessToPageVariables.png
 [10]: http://www.blueskyonmars.com/images/2010/08/HidingTheHeader.png
 [11]: http://www.blueskyonmars.com/images/2010/08/ObjectInspector.png
 [12]: https://lists.mozilla.org/listinfo/dev-apps-firefox
 [13]: mailto:kevin@kevindangoor.com