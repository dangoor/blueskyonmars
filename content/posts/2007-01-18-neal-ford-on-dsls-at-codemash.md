---
title: Neal Ford on DSLs at CodeMash
author: Kevin Dangoor
type: post
date: 2007-01-18T17:50:13+00:00
url: /2007/01/18/neal-ford-on-dsls-at-codemash/
categories:
  - Software Development

---
Neal Ford, from Thoughtworks, did the opening keynote session at CodeMash. His talk was about language oriented programming and domain specific languages as the next evolutionary step for programming. (LOP and DSL were both terms coined by Martin Fowler, also of Thoughtworks). Neal traced through the history of programming languages to determine how we got to the languages we have today. Then he started in on DSLs and had some compelling examples of DSLs in the real world (Starbucks, Waffle House hash browns, etc.).

He used log4j configuration (which also applies to Python logging) as an example of something that is just begging to be turned into a DSL. (Which he does in Java for log4j&#8230; yes, you can make DSLs of a sort with Java.) One area where this has been picked up in the static language world is in the mock object libraries, where expectations are described using something more like a DSL.

Neal talks about all of the XML configuration files we have today as DSLs and also contends that Unix, if it was invented today, would have XML configuration files all over the place. Ick. I&#8217;m of the opinion that XML makes for painful and verbose DSLs, and would rather have much more pleasant DSLs.

He cited Martin Fowler&#8217;s strategy pattern DSL example where he talks about a reader for positional record files of the type you often get from mainframes. He made a Ruby version of that same example that was quite nice and readable, and I thought this was the perfect example of why you wouldn&#8217;t want to create such DSLs with XML. XML would have been far harder to read.

The last part of the talk went into the notion of &#8220;Language Workbenches&#8221;, a new category of tool that puts the abstract representation of code at the center of the universe (rather than your source) and then puts different kinds of projections on top of the abstract representation. JetBrain&#8217;s Meta Programming System lets you create DSLs with their own highlighting editors that support pull downs and context sensitive error displays.

None of the language workbenches are ready for prime time yet. It&#8217;s something to watch for, but nothing prevents us from making DSLs in our existing languages where it makes sense to do so.

I think it will be interesting to see how DSLs evolve over time (literally: when you make a DSL, how well do you maintain backwards compatibility?)

Neal&#8217;s talk was thought provoking in that designing around the vocabulary of a domain is not the main way most of us design.