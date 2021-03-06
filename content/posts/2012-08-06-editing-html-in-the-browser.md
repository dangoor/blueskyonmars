---
title: Editing HTML in the browser
author: Kevin Dangoor
type: post
date: 2012-08-06T18:43:02+00:00
url: /2012/08/06/editing-html-in-the-browser/
categories:
  - Mozilla
  - Software Development

---
Live editing of CSS in the browser works great. You get to see your changes _immediately_, and there&#8217;s nothing like [live feedback][1] to keep you rolling, right? The Style Editor in Firefox makes it really easy to [edit your CSS and save][2] when you&#8217;ve got everything looking just right.

CSS is purely [declarative][3], which makes it a bit more straightforward to implement live editing. Swap out the rules and the new rules take effect without weird side effects.

HTML is declarative as well, but there are two problems with &#8220;live HTML editing&#8221;:

  1. You&#8217;re changing the Document Object Model (DOM), not HTML
  2. What you&#8217;re changing is often not the same as what you started out with

### DOM vs. HTML

I won&#8217;t dwell on this, but the first problem is that even if you&#8217;re looking at a &#8220;static HTML file&#8221;, once the browser grabs onto that HTML it turns it into a DOM. The browser&#8217;s tools will show you what looks like HTML, but it&#8217;s really just a visual representation of the DOM. JavaScript can manipulate the DOM and change things entirely from what was sent down the wire. JavaScript can also add properties to DOM objects that don&#8217;t even appear in the &#8220;HTML view&#8221; that the browser shows you.

Of course, using Firebug (and, [soon enough, Firefox as well][4]) you can make live changes to the DOM in an HTML-like view. Some kinds of these changes may mess up things like event handlers, but you can still try out your changes.

The real problem is&#8230;

### What you&#8217;re changing is not what you started with

A fundamental bit of building a webapp is taking some data and plugging it into an HTML/DOM structure so that the user can see it and interact with it. Consider this view of [Mozilla&#8217;s GitHub repositories][5]:

[<img class="aligncenter size-full wp-image-2932" title="Mozilla GitHub Repos" src="http://www.blueskyonmars.com/images/2012/08/Mozilla-GitHub-Repos.png" alt="" width="461" height="564" srcset="https://www.blueskyonmars.com/images/2012/08/Mozilla-GitHub-Repos.png 461w, https://www.blueskyonmars.com/images/2012/08/Mozilla-GitHub-Repos-245x300.png 245w" sizes="(max-width: 461px) 100vw, 461px" />][6]Let&#8217;s say I wanted to add a new bit of information that&#8217;s already in the database into this compact repository view. I could open up Firebug and add it to the DOM. This would at least allow me to try out different DOM structures and get the styling right. However, I&#8217;d need to go back to my server code (I&#8217;m assuming the view above is generated by GitHub&#8217;s Rails code) and make the change for real there. Plus, I&#8217;d only get to see how the change looks on one of the elements, until I&#8217;ve updated the server and reloaded.

Back when I was working on [TurboGears][7] (2005), almost all of the stuff that ended up in the DOM got there from HTML that was rendered on the server.  Then, as today, people used all kinds of template engines on the server to take a mass of data and munge that into some kind of HTML structure for the browser to display.

Many developers have been experimenting ([with varying degrees of success][8]) with moving the conversion from &#8220;hunk of data&#8221; to DOM into the browser. That means that the browser will take a hunk of data, combine it with some sort of template and then update the DOM with the new content[<sup>[1]</sup>][9]{#refmark-1.fn-ref-mark}. So, the browser has the data _and_ the template in hand.

What if the browser tracked the relationship between data, template and elements of the DOM? Wouldn&#8217;t it be cool to fire up the Page Inspector, point it at one of those repositories in the screenshot above and then tweak the _template_ rather than tweaking the DOM? If you add that new field to the template, then all of the repositories on screen would immediately be refreshed.

Even better, once you&#8217;ve got everything looking the way you want, you could save your template to disk[<sup>[2]</sup>][10]{#refmark-2.fn-ref-mark}, much like you can with a CSS file in our Style Editor right now.

## How do we get there from here?

The creators of [one of the MV* frameworks][11] could make a browser-based editor that understands the templates used in their system and lets you make on-the-fly tweaks. The disadvantage to that approach is that it only benefits that one framework. And, even for users of that framework, that editor would stand alone from the rest of the browser-based tools (would they create their own CSS editing in addition to template editing?)

Another way to go would be something like the [Model-driven Views][12] (MDV) project. The idea there is to add templating directly to HTML and the web platform. MDV is nice because changes to the data are automatically propagated back into what the browser displays. I don&#8217;t know if MDV would also automatically propagate changes to the template back into the display, but that would be the idea.

There are _many_ different opinions on how templates should work. I&#8217;d be happy if we pick _one_ approach, make it a part of the web and enable smooth live editing of the entire appearance of our sites and apps.

## Feedback

Mardeg writes:

> The &#8220;Model-driven Views&#8221; puts <template> tags inside the html and relies on them being parsed with javascript, whereas it might be feasible to use javascript to generate/alter a template from combined MicroData and explicit role attributes already existing within the page, which wouldn&#8217;t affect how the page is viewed with javascript disabled.

If MDV becomes a part of HTML (as in &#8220;baked into the browser&#8221;), then it may not rely on JS at all. I like the idea of being able to combine a template with microdata. Personally, I think we&#8217;re reaching a point where if you want to run web applications you really need to have JS on.

<div id="footnote-list" style="display:inherit">
  <span id=fn-heading>Footnotes</span> &nbsp;&nbsp;&nbsp;(&crarr; returns to text)</p> 
  
  <ol>
    <li id="footnote-1" class="fn-text">
      I&#8217;m sure some people just build the DOM imperatively with JavaScript, but I&#8217;m going to ignore that case for this post.<a href="#refmark-1">&crarr;</a>
    </li>
    <li id="footnote-2" class="fn-text">
      OK, this certainly depends on where and how the templates are actually stored. I would personally make it a goal to be able to easily save (or at least copy/paste) templates back to their origins.<a href="#refmark-2">&crarr;</a>
    </li>
  </ol>
</div>

 [1]: http://vimeo.com/36579366
 [2]: www.youtube.com/watch?v=1kAclc-ltdM
 [3]: http://en.wikipedia.org/wiki/Declarative_programming
 [4]: https://bugzilla.mozilla.org/show_bug.cgi?id=777085
 [5]: http://github.com/mozilla/
 [6]: http://www.blueskyonmars.com/images/2012/08/Mozilla-GitHub-Repos.png
 [7]: http://en.wikipedia.org/wiki/TurboGears
 [8]: http://engineering.twitter.com/2012/05/improving-performance-on-twittercom.html
 [9]: #footnote-1
 [10]: #footnote-2
 [11]: http://blog.stevensanderson.com/2012/08/01/rich-javascript-applications-the-seven-frameworks-throne-of-js-2012/
 [12]: http://code.google.com/p/mdv/