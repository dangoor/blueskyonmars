---
title: 'Bespin: code in the cloud'
author: Kevin Dangoor
type: post
date: 2009-02-15T01:30:19+00:00
url: /2009/02/14/bespin-code-in-the-cloud/
categories:
  - JavaScript
  - Python
  - Software Development

---
Despite working for an [open source company][1], I have been pretty quiet here about what I&#8217;ve been doing in the Mozilla Labs web developer tools group. No more. We&#8217;ve gone public!

[Mozilla Labs Â» Blog Archive Â» Introducing Bespin][2]

> Bespin proposes an open extensible web-based framework for code editing that aims to increase developer productivity, enable compelling user experiences, and promote the use of open standards.

I started working on Bespin as soon as I joined Mozilla, hitting the ground running with a new Python server. [Ben and Dion][3] had already done a lot of work and experimentation on Bespin prior to joining Mozilla in December, so I must confess that I am still fairly ignorant about the Canvas-based magic that they&#8217;re doing in the UI. But, Bespin has an architecture that lends itself well to selective ignorance: the server provides a [RESTful API][4], and the client is responsible for all of the presentation. For their part, Ben and Dion have been able to be blissfully ignorant about the inner workings of the Python server.

Of course, I&#8217;m not a JavaScript noob and have done some work in the client, but my focus has been the server. Now that we&#8217;re out in the open, you can definitely expect that we&#8217;ll be talking more about how things work and how you can bend Bespin to your will. Bespin is honest to goodness [open source][5] ([MPL][6]-licensed), so it becomes an open and collaborative effort starting right away.

The initial reaction has been fantastic. There are tons of people hanging out in #bespin on irc.mozilla.org, and the [mailing list][7] has grown to a couple hundred members already. Thanks to everyone for jumping in with your thoughts and patches!

Here&#8217;s some of the coverage:

[Dion&#8217;s post at Ajaxian][8]:

<img style="max-width: 800px;" src="http://ajaxian.com/wp-content/uploads/editorofourdreams.png" />

From [Dion&#8217;s personal blog][9]:

> Foolish chaps and companies have come to me in the past thinking that open source will be a silver bullet for â€œgetting other people to do our work.â€ Those that have been involved in open source know that it isnâ€™t the case. It is often more work. But, it is worth it.

From [Ars Technica][10]:

> The project is still at an early stage of development and there is clearly a lot of work to be done before it will be able to deliver the same practical value as existing desktop editors. Despite the limitations, it shows an enormous amount of promise and has the potential to eventually deliver a user experience that rivals even the best text editors.

From [Five Questions with Dion Almaer][11]:

> Now the browsers are moving fast again and building a first class platform for us to develop, the Open Web Platform. Instead of getting bogged down thinking about what IE 6 gives you, take some time to think about what you could build with the latest technology. I realise that you have to be pragmatic and get things working with your audience, but browsers are changing, and so are expectations.

From [What Mozilla&#8217;s Bespin Bespeaks][12] (ComputerworldUK):

> You can see that Bespin is ticking all the Mozilla boxes, but what&#8217;s also striking is that this is a Web-based project: Mozilla is entering the cloud. It&#8217;s a further shift to viewing the Web as a platform for doing, well, just about anything. Clearly, against that background, open standards are even more important. And not only for the code: another issue that Mozilla will need to start addressing publicly is that of open data. As more stuff moves into the cloud, it become imperative to establish minimum standards for access to the data that is held there. I look forward to hearing Mozilla&#8217;s views on the subject. 

While I certainly don&#8217;t speak for Mozilla, I would be _extremely surprised_ if there&#8217;s anyone at Mozilla that believes that users should have anything less than full access and ability to take their data with them. There can be technical issues involved in providing the data, but the data should be available in some reasonable form. Bespin, for its part, makes it easy to export a project in a tarball or zipfile.

I was surprised to see [Bespin covered even on Lifehacker][13]:

> Primarily, Bespin is a text editorâ€”the kind you&#8217;d use for editing code or managing [text-based todos][14]. Using Bespin, developers could collaborate on projects through a unified interface (that still supports plugins!) no matter where they areâ€”so long as they&#8217;ve got a browser.

[cnet has the story,][15] too:

> For example, what about integration with open-source software repositories? If it&#8217;s flexible enough, Bespin could essentially act as a source code viewer that repositories such as SourceForge or Google Code could employ. 

A [nice writeup on the ReadWriteWeb][16] as well:

> It&#8217;s clear that a great deal of thought and attention went into this early version &#8211; and it&#8217;s a safe bet that it will only get more impressive as time goes on.

RWW last month surprised me with [their coverage of me joining Mozilla][17].

I&#8217;m having a great time at Mozilla so far, and it&#8217;s great to be out in the open working with so many people now on Bespin and [ServerJS][18].

<div class="zemanta-pixie">
  <img class="zemanta-pixie-img" src="http://img.zemanta.com/pixy.gif?x-id=da16a7ba-73bb-4ac9-83a3-f954ff3f2b0c" />
</div>

 [1]: http://www.mozilla.com/
 [2]: http://labs.mozilla.com/2009/02/introducing-bespin/
 [3]: http://www.ajaxian.com
 [4]: https://wiki.mozilla.org/BespinServerAPI
 [5]: http://hg.mozilla.org/labs/bespin/
 [6]: http://www.mozilla.org/MPL/
 [7]: http://groups.google.com/group/bespin/
 [8]: http://ajaxian.com/archives/bespin-a-new-mozilla-labs-experimental-extensible-code-editor-using-canvas
 [9]: http://almaer.com/blog/launching-bespin-feeling-light-as-a-cloud
 [10]: http://arstechnica.com/open-source/news/2009/02/ide-in-the-cloud-mozilla-labs-browser-based-ide-prototype.ars
 [11]: http://opensourcereleasefeed.com/interview/show/five-questions-with-dion-almaer-co-creator-of-mozilla-bespin
 [12]: http://www.computerworlduk.com/community/blogs/index.cfm?entryid=1858&blogid=14
 [13]: http://lifehacker.com/5152999/mozilla-bespin-is-a-killer-web+based-text-editor
 [14]: http://lifehacker.com/software/text/geek-to-live-list-your-life-in-txt-166299.php
 [15]: http://news.cnet.com/8301-17939_109-10163516-2.html
 [16]: http://www.readwriteweb.com/archives/bespin_html_editor_cloud.php
 [17]: http://www.readwriteweb.com/jobwire/2009/01/mozilla-developer-tools-lab-hi.php
 [18]: http://groups.google.com/group/serverjs