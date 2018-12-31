---
title: document.body vs. document.documentElement in IE
author: Kevin Dangoor
type: post
date: 2005-03-24T18:24:43+00:00
url: /2005/03/24/documentbody-vs-documentdocumentelement-in-ie/
categories:
  - Software Development

---
Ahh, cross-browser fun. Even when you&#8217;re only supporting very recent browsers (my targets are IE5.5+, Moz/Firefox and Safari), there&#8217;s always cross-browser joy to be had. I was positioning a div in response to a click, and it worked just dandy in Firefox, but gave an error in IE. I was using event.pageX and event.pageY, which IE knows nothing about. I found many references that said to use event.clientX+document.body.scrollLeft, but it was clear that document.body.scrollLeft was always zero. I finally found the answer here: [Event handling in the DOM Part 2- Page 3/4][1]

> For IE, the above code adds the scroll offset values of both the HTML tag (represented by document.documentElement) and the BODY tag (represented by document.body). This is because IE 5.5 uses the BODY as a base for rendering and measuring offsets, as does IE 6 when in compatibility mode. But in standards-compliant mode IE 6 instead uses the HTML tag as a base.

So, if you want the document position of an event, the formula is: x = event.clientX + document.documentElement.scrollLeft + document.body.scrollLeft. (y is left as an exercise for the reader).

 [1]: http://www.javascriptkit.com/dhtmltutors/domeventp2-3.shtml "Event handling in the DOM Part 2- Page 3/4"