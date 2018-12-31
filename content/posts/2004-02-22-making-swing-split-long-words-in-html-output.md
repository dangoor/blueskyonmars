---
title: Making Swing split long words in HTML output
author: Kevin Dangoor
type: post
date: 2004-02-23T04:30:06+00:00
url: /2004/02/22/making-swing-split-long-words-in-html-output/
categories:
  - Software Development

---
Keith on the Joustlog has a nice tip for [joustlog: How to make the Swing HTML renderer split long words when wrapping][1]. Not something I need at the moment, but certainly a good thing to keep in mind. (In case the link rots, the basic idea was to subclass HTMLEditorKit, creating a new ParagraphView that gets returned by a new ViewFactory.)

 [1]: http://joust.kano.net/weblog/archives/000074.html "joustlog: How to make the Swing HTML renderer split long words when wrapping"