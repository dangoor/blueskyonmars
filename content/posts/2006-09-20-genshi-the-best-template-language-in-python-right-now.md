---
title: 'Genshi: the best template language in Python right now'
author: Kevin Dangoor
type: post
date: 2006-09-20T13:35:18+00:00
url: /2006/09/20/genshi-the-best-template-language-in-python-right-now/
categories:
  - Python
  - TurboGears

---
Christopher Lenz announced a new version of [Genshi][1] a couple of days ago. Genshi is the template language that was formerly known as Markup. A good way to think about it is that it&#8217;s Kid 2.0. The latest version includes a feature I was wishing for in Kid: [plaintext templating][2]. Take a look at the doctest for it:

    >>> tmpl = TextTemplate('''Dear $name,
    ...
    ... We have the following items for you:
    ... #for item in items
    ...  * $item
    ... #end
    ...
    ... All the best,
    ... Foobar''')
    >>> print tmpl.generate(name='Joe', items=[1, 2, 3]).render('text')
    Dear Joe,
    <blankline>
    We have the following items for you:
     * 1
     * 2
     * 3
    </blankline><blankline>
    All the best,
    Foobar</blankline>

This uses all of Genshi&#8217;s infrastructure, so the kinds of expressions and things that you&#8217;re used to when generating HTML and XML will still work here. HTML and XML definitely remain Genshi&#8217;s forte and if you&#8217;re not generating those formats at all, you&#8217;d likely want to choose a different language. (You can get higher performance when you don&#8217;t care about document structure&#8230;)

Genshi builds on Kid&#8217;s template language with flexible includes via xinclude, template matching via XPath expressions, much better error reporting and better performance to boot. The Trac project is currently in the process of converting over to Genshi, and it&#8217;s in plan that TurboGears will convert to Genshi in TG 1.1. (You can, of course, use Genshi _now_ with TurboGears, and you&#8217;ll certainly be able to continue using Kid.)
  
Genshi owes a lot to Kid&#8217;s original design, but it has definitely moved the state of the art forward a good deal.

 [1]: http://genshi.edgewall.org
 [2]: http://genshi.edgewall.org/wiki/ApiDocs/genshi.template#genshi.template:TextTemplate