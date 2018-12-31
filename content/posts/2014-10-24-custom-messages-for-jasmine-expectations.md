---
title: Custom messages for Jasmine expectations
author: Kevin Dangoor
type: post
date: 2014-10-25T03:19:21+00:00
url: /2014/10/24/custom-messages-for-jasmine-expectations/
linked_list_url:
  - https://github.com/avrelian/jasmine-custom-message
categories:
  - JavaScript
  - Linkage
format: link

---
[jasmine-custom-message][1] gives you a &#8220;custom failure message on any jasmine assertion&#8221;:

    describe('the story', function() {
      it('should finish ok', function() {
        since('all cats are grey in the dark').
        expect('tiger').toEqual('kitty'); // => 'all cats are grey in the dark'
      });
    });
    

Overall, I like [Jasmine][2] as a testing library, but this particular limitation has really bothered me.

 [1]: https://github.com/avrelian/jasmine-custom-message
 [2]: http://jasmine.github.io/