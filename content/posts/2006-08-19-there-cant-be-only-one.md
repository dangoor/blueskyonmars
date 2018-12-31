---
title: There can’t be only one.
author: Kevin Dangoor
type: post
date: 2006-08-19T13:30:42+00:00
url: /2006/08/19/there-cant-be-only-one/
categories:
  - Python
  - TurboGears

---
I guess I&#8217;d better give up now. Guido announced at SciPy that [Django is the &#8220;standard&#8221; web framework for Python][1]. How&#8217;s that for a first two sentences of a blog post? Of course, only one of those two sentences is accurate.

According to the blog post I linked to above, Guido &#8220;hopes that Django and TurboGears will converge&#8221;. _Sigh_. Someone please tell me that Guido hasn&#8217;t fallen for the &#8220;Python is losing to Ruby because Ruby only has one web framework&#8221; argument. I&#8217;m pretty sure he hasn&#8217;t fallen for that argument, but just generally thinks it would be a good thing. Django and TurboGears converging would be very much akin to Python and Ruby converging (Tim O&#8217;Reilly would probably advocate that, since book sales indicate that Python is waning). They address similar problem spaces and even have some similar approaches in spots, but that&#8217;s really a superficial view of the whole.

Guido&#8217;s attraction to Django started with [Django&#8217;s template engine][2]. He compared it with Cheetah and said, toward the bottom:

> I didn&#8217;t find too many other templating solutions. TurboGears uses Kid which XML-based, like Nevow, TAL etc. IMO these are no contenders because they are XML-based. As the Django folks mention, they use templates to generate non-HTML text files as well. And even if they could be used for this, the verbosity of the XML syntax and the inability to do a proper if-then-else in XML make template writing using XML a non-starter.

For generating HTML, I find Kid to be a natural fit. I think it&#8217;s more natural than TAL and Nevow because the programmer just puts standard Python expressions in the right places in their templates (rather than some other kind of expression). Being able to write good, clean XHTML and produce fine HTML for the browser is a great feature and a great way to work. In practice, because I don&#8217;t go overboard writing code in templates, so if-then-else has not been a real problem. And, [Markup shows a fairly clean way to do it][3] anyhow.

And, certainly, generating non-HTML text files with Kid is suboptimal. First of all, I&#8217;d say again that this is not actually a big problem in practice. Seriously. It&#8217;s just not something that comes up much on the mailing list. Besides, TurboGears makes it _trivial_ to use one of many other template languages (including Django&#8217;s) for generating non-HTML formats. In fact, you can even do it in one method:

<pre>@expose("myproj.templates.showstuff")
@expose("cheetah:myproj.templates.textstuff", accept_format="text/plain")
def index(self):
    return dict(foo="5")
</pre>

When you hit that controller method, by default you&#8217;ll get that dictionary plugged into the Kid template to produce HTML. If your browser sends an &#8220;Accept: text/plain&#8221;, TG will have Cheetah use the same code to generate a plain text view. Nice, huh?

TurboGears has a collection of APIs and idioms that I think make it great fun to work with, and I know others agree with me. Django has its own collection of features that others like working with. That&#8217;s fine by me, and it&#8217;s not likely to change any time soon.

With TurboGears, I definitely do not suffer from [Not Invented Here][4]. In Django&#8217;s defense, at the time they started they simply didn&#8217;t have the options available that I did when I started TurboGears. But, the Python community continues to evolve, innovate and produce incredible products. TG will benefit greatly from these projects, but it&#8217;s unclear that Django would follow suit.

Mike Bayer&#8217;s [SQLAlchemy][5], simply put, kicks the butt of Django&#8217;s ORM (and that of Rails, as well). SQLAlchemy is already a solid second-class citizen in TurboGears, and will be a first-class citizen soon enough. Christopher Lenz saw the good in Kid and thought he could build a better Kid with [Markup][6]. Though it&#8217;s a young project, it looks great and has impressive results. Julian Krause liked CherryPy&#8217;s quick-and-easy URL traversal, but wanted to break it down to a WSGI core so he created [RhubarbTart][7]. Meanwhile, Robert Brewer has completely retooled [CherryPy&#8217;s][8] easy &#8220;filters&#8221; feature for CherryPy 3.0. And, for those who like their URL traversal in separate files with regexes, there&#8217;s always Ben Bangert&#8217;s [Routes][9].

All of the things that I mentioned in that paragraph are not vaporware. With the exception of RhubarbTart, these are things that you can use with TurboGears now and that will likely be included directly with a future TG release. TG has had code contributions from quite a few people, but these things are all steps forward that have occurred completely outside of TurboGears but remain a natural fit for TG.

At EuroPython, during the Web Framework Shootout, we (Simon Willison, Phillip von Weitershausen and I) were taking questions from the audience and someone asked if we thought that TurboGears and Django would merge. My response now is the same as it was then: not very likely. Both projects have their own ideas and approaches and trying to force fit them just wouldn&#8217;t work.

Today&#8217;s TurboGears 0.9a9 release will likely be the last 0.9 alpha before 1.0 beta 1 comes out. Though many TurboGears users have been running the 0.9/1.0 code for some time, I&#8217;m looking forward to finally unveiling it more here, on TurboGears.org and in &#8220;Rapid Web Applications with TurboGears&#8221;. My thanks, as always, goes to the many TurboGears developers that make the project possible.

 [1]: http://pyre.third-bit.com/blog/archives/613.html
 [2]: http://www.artima.com/weblogs/viewpost.jsp?thread=146606
 [3]: http://markup.edgewall.com/wiki/MarkupTemplates#py:choosepy:whenpy:otherwise
 [4]: http://en.wikipedia.org/wiki/Not_Invented_Here
 [5]: http://www.sqlalchemy.org/
 [6]: http://markup.edgewall.com/
 [7]: http://rhubarbtart.org
 [8]: http://www.cherrypy.org/
 [9]: http://routes.groovie.org/