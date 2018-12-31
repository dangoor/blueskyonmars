---
title: Turning web docs into printable docs
author: Kevin Dangoor
type: post
date: 2005-08-03T13:02:17+00:00
url: /2005/08/03/turning-web-docs-into-printable-docs/
keywords:
  - css,xsl,xml,xhtml
categories:
  - Software Development

---
Quite a bit of documentation is written in HTML these days, since quite a bit of it is designed to be on the web. HTML doesn&#8217;t always work out well for the printed page, primarily because you need to be able to properly refer to page numbers in a large document. You need that capability for tables of contents, indices and references to illustrations. Print is also better if you have at least a little control over where a pagebreak occurs.

All hope is not lost, however. There is a page on the fabulous css-discuss wiki that talks [about print stylesheets][1], and goes through the capabilities and pitfalls. It sounds like Opera currently has the best browser support for print style sheets.

Two other solutions worthy of consideration, though, are: [CSStoXSLFO][2] and [Prince][3]. 

CSStoXSLFO converts an XML document with a stylesheet into a PDF by way of XSL formatting objects. It supports some of the CSS page tags and provides a means to do references to page numbers. And it&#8217;s free!

Prince is not free ($349 for a single user license), but sounds very capable and has a free trial so that you can really give it a whirl.

Both of these products include specific support for turning XHTML into quality PDFs.

 [1]: http://css-discuss.incutio.com/?page=PrintStylesheets
 [2]: http://www.re.be/css2xslfo/
 [3]: http://www.princexml.com/