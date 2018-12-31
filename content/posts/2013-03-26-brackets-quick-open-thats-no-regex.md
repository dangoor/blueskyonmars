---
title: 'Brackets Quick Open: That’s No Regex!'
author: Kevin Dangoor
type: post
date: 2013-03-26T15:39:58+00:00
url: /2013/03/26/brackets-quick-open-thats-no-regex/
categories:
  - Brackets

---
Ever since I first used TextMate several years ago, I&#8217;ve been hooked on &#8220;Quick Open&#8221; (the feature that lets you jump to any file in your project with just a few keystrokes). I have worked on [Brackets&#8217;][1] version of this feature and I thought I&#8217;d take advantage of Brackets being open source to talk about how it works.

The current incarnation of Quick Open in Brackets is the third. It started very simply, just matching substrings in the filename if I remember correctly. Today, it relies on a module called [StringMatch][2] which:

  * searches across the entire file path, not just the name
  * gives preference to matches in the last part of the path (the name)
  * gives preference to matches on &#8220;special characters&#8221;
  * produces a score that attempts to get at a most likely match

Those &#8220;give preferences&#8221; bits are what make StringMatch a lot trickier than just applying a regex and my goal with this post is to touch upon some of what went in to producing good results. While working on Quick Open, which is in `src/search/QuickOpen.js`, I wanted to be able to type &#8220;qo&#8221; and have that file be the top match. With thousands of files in our repository, there are doubtless quite a few that match &#8220;qo&#8221;. Getting to the _best_ match was key.

<figure>  ![StringMatch in Action][3]<caption>StringMatch in Action</caption> </figure> 

## The stringMatch function

The StringMatch module has a function called [`stringMatch`][4] that takes a string to match against, the query string and an optional &#8220;specials&#8221; data structure. The function is stateless and doesn&#8217;t use any indexes (see the section on speed toward the end).

stringMatch returns information about the match (if the query matches the string) to allow highlighting and sorting by score. stringMatch itself doesn&#8217;t do very much. It&#8217;s job is to glue together the other functions in the module.

## Special Characters

I mentioned a &#8220;specials&#8221; data structure and how preference is given to &#8220;special&#8221; characters. What are these mysterious special beings? As stated in the comments for [`findSpecialCharacters`][5]:

  * the first character
  * &#8220;/&#8221; and the character following the &#8220;/&#8221; (path separators)
  * &#8220;_&#8221;, &#8220;.&#8221; and &#8220;-&#8221; and the character following it (other characters used to separate parts of filenames)
  * an uppercase character that follows a lowercase one (think camelCase)

So, the job of `findSpecialCharacters` is to create a list of indexes of these special characters of the string that is being checked against the query. Additionally, `findSpecialCharacters` returns the index into the list of special characters that represents the beginning of the &#8220;last segment&#8221;. The code in `findSpecialCharacters` is straightforward, simply reading each character of the string and keeping track of what it sees as it goes along.

The `stringMatch` function will call `findSpecialCharacters` if it&#8217;s not given the specials data structure at the beginning. But, as we&#8217;ll see in the section on speed, hanging on to the result of `findSpecialCharacters` gives us a bit of a boost.

## Searching the String

`stringMatch` calls a function called [`_wholeStringSearch`][6] which is responsible for taking the string and the query and producing the list of matches. This happens in two steps:

  1. the query is run against the &#8220;last segment&#8221; (the file name)
  2. anything that&#8217;s left over from that search is matched against the part of the string before the last segment

There&#8217;s a separate function ([`_lastSegmentSearch`][7]) that&#8217;s responsible for trying the query against the last segment, which is not as simple as it might seem.

With a query of &#8220;qo&#8221;, it&#8217;s easy to see how that can match in the last segment of `src/search/QuickOpen.js`. But, imagine that I typed &#8220;sqo&#8221; instead. &#8220;sqo&#8221; is clearly still a match, but searching for &#8220;sqo&#8221; in just the last segment fails. So, it seeks out the largest match that it can get in the last segment. It would find that &#8220;qo&#8221; matches in `QuickOpen.js` and hunt starting at the beginning of the string for the remaining &#8220;s&#8221;.

It&#8217;s entirely possible that the entire query doesn&#8217;t match against the last segment, which means that all of the work of checking each substring of the query against the last segment was a waste. On the other hand, users will generally have a certain file in mind that they want to open and I&#8217;d be surprised if they weren&#8217;t typing any characters from the file name.

## Generating the Matches

The [`_generateMatchList`][8] function is the craziest bit in the file. There&#8217;s a reason it has 70 lines of comments preceding the function.

Why does it have to be so crazy? It all comes back to those preferences of which characters to search first. If I have a file called `QuoteOpus.js` and I search for &#8220;qo&#8221;, I want the match to be **Q**uote**O**pus, not **Q**u**o**teOpus. I also want `QuickOpen.js` to be a better match than `Quote.js`, even though both of those match &#8220;qo&#8221;.

There&#8217;s a loop toward the bottom of the function that is responsible for doggedly trying everything until it finds a match that works:

    #!javascript
    
        while (true) {
            // keep looping until we've either exhausted the query or the string
            while (queryCounter < query.length && strCounter < str.length && strCounter <= deadBranches[queryCounter]) {
                if (state === SPECIALS_MATCH) {
                    if (!findMatchingSpecial()) {
                        state = ANY_MATCH;
                    }
                }
    
                if (state === ANY_MATCH) {
                    // we look character by character for matches
                    if (query[queryCounter] === str[strCounter]) {
                        // got a match! record it, and switch back to searching specials
                        queryCounter++;
                        result.push(new NormalMatch(strCounter++));
                        state = SPECIALS_MATCH;
                    } else {
                        // no match, keep looking
                        strCounter++;
                    }
                }
            }
    
            // if we've finished the query, or we haven't finished the query but we have no
            // more backtracking we can do, then we're all done searching.
            if (queryCounter >= query.length || (queryCounter < query.length && !backtrack())) {
                break;
            }
        }
    

We&#8217;re going to keep looking at characters until we hit the end of the string or the end of the query. We start out looking for matches among the special characters. Failing that, we&#8217;ll start looking character-by-character through the string until we find a match among the non-special characters. Searching for &#8220;qo&#8221; in `Quote.js` is going to find a match at the &#8220;Q&#8221; which it&#8217;s perfectly happy with. Then, it&#8217;ll try to match the &#8220;o&#8221; against the &#8220;.&#8221; (the next special character). Nope. No luck with the &#8220;j&#8221;, which is also special because it comes after the &#8220;.&#8221;. So, then it goes back and checks out the &#8220;u&#8221; before finally finding the &#8220;o&#8221; that matches.

Finding the special character matches is pretty straightforward, because we already have a list of indexes into the string where the special characters are located. The [`findMatchingSpecial`][9] function uses a counter to keep track of which special matched last and then proceeds to walk through the list of specials from there.

I rather wish the story could end there: scan through the matching specials and then scan through the non-special characters when that fails. In fact, I did initially end there. But, it turned out that there were cases that I missed entirely when I did that. And that&#8217;s where the `deadBranches` and `backtrack()` come into play in the loop above.

Here&#8217;s the example pulled from the comments of `_generateMatchList`:

    /*
     * A contrived example will help illustrate how the searching and backtracking works. It's a bit long,
     * but it illustrates different pieces of the algorithm which can be tricky. Let's say that we're
     * searching the string "AzzBzzCzdzezzDgxgEF" for "abcdex".
     *
     * To start with, it will match "abcde" from the query to "A B C D E" in the string (the spaces 
     * represent gaps in the matched part of the string), because those are all "special characters".
     * However, the "x" in the query doesn't match the "F" which is the only character left in the
     * string.
     * 
     * Backtracking kicks in. The "E" is pulled off of the match list.
     * deadBranches[4] is set to the "g" before the "E". This means that for the 5th
     * query character (the "e") we know that we don't have a match beyond that point in the string.
     *
     * To resume searching, the backtrack function looks at the previous match (the "D") and starts
     * searching in character-by-character (ANY_MATCH) mode right after that. It fails to find an
     * "e" before it gets to deadBranches[4], so it has to backtrack again.
     *
     * This time, the "D" is pulled off the match list.
     * deadBranches[3] is set to the "z" before the "D", because we know that for the "dex" part of the
     * query, we can't make it work past the "D". We'll resume searching with the "z" after the "C".
     *
     * Doing an ANY_MATCH search, we find the "d". We then start searching specials for "e", but we
     * stop before we get to "E" because deadBranches[4] tells us that's a dead end. So, we switch
     * to ANY_MATCH and find the "e".
     *
     * Finally, we search for the "x". We don't find a special that matches, so we start an ANY_MATCH
     * search. Then we find the "x", and we have a successful match.
     */
    

In the process of working on this, I read a bit about [dynamic programming][10], which is an interesting topic and one of the ways in which you can solve the [longest common substring][11] problem (something I initially thought might be valuable for StringMatch). The idea that I ended up applying is that when we&#8217;re searching the string we can keep track of parts of the query that we&#8217;ve tried and found do not work past a certain point of the string. Those are the `deadBranches`. When we hit one, we know we need to backtrack farther.

What does [backtracking][12] look like?

        // This function implements the backtracking that is done when we fail to find
        // a match with the query using the "search for specials first" approach.
        //
        // returns false when it is not able to backtrack successfully
        function backtrack() {
    
            // The idea is to pull matches off of our match list, rolling back
            // characters from the query. We pay special attention to the special
            // characters since they are searched first.
            while (result.length > 0) {
                var item = result.pop();
    
                // nothing in the list? there's no possible match then.
                if (!item) {
                    return false;
                }
    
                // we pulled off a match, which means that we need to put a character
                // back into our query. strCounter is going to be set once we've pulled
                // off the right special character and know where we're going to restart
                // searching from.
                queryCounter--;
    
                if (item instanceof SpecialMatch) {
                    // pulled off a special, which means we need to make that special available
                    // for matching again
                    specialsCounter--;
    
                    // check to see if we've gone back as far as we need to
                    if (item.index < deadBranches[queryCounter]) {
                        // we now know that this part of the query does not match beyond this
                        // point
                        deadBranches[queryCounter] = item.index - 1;
    
                        // since we failed with the specials along this track, we're
                        // going to reset to looking for matches consecutively.
                        state = ANY_MATCH;
    
                        // we figure out where to start looking based on the new
                        // last item in the list. If there isn't anything else
                        // in the match list, we'll start over at the starting special
                        // (which is generally the beginning of the string, or the
                        // beginning of the last segment of the string)
                        item = result[result.length - 1];
                        if (!item) {
                            strCounter = specials[startingSpecial] + 1;
                            return true;
                        }
                        strCounter = item.index + 1;
                        return true;
                    }
                }
            }
            return false;
        }
    

The basic idea here is that we see that we&#8217;ve reached a point after which our query doesn&#8217;t match the remaining bit of the string, so we rewind any matches that we found to take us back before the last `deadBranches` point. After we&#8217;ve done that, we hang on to our newly identified &#8220;if you reach this part of the string with that part of the query, all hope is lost&#8221; point.

`_generateMatchList` returns a list of `SpecialMatch` and `NormalMatch` objects. We just need to return the list of matched indexes and the type of object shows whether the index was a special character or not (which is used in scoring).

## Turning Matched Characters into Ranges and a Score

The [`_computeRangesAndScore`][13] function does a fairly straightforward transformation of the matched characters list into a set of ranges in the string that are used in highlighting which parts matched and the final score. There&#8217;s nothing very magical here, but you can see that there are 7 different components that go into the score at this point:

        if (DEBUG_SCORES) {
            scoreDebug = {
                special: 0,
                match: 0,
                lastSegment: 0,
                beginning: 0,
                lengthDeduction: 0,
                consecutive: 0,
                notStartingOnSpecial: 0
            };
        }
    

You can also see that with 7 different parts of the score, being able to set a flag to see how each part adds to the whole would come in handy. Coming up with the exact numbers used in scoring was not very scientific, instead coming as a result of looking at various comparisons and adjusting the parameters until the results felt like the kind of results we wanted to see.

## Test-driven to Get It Right

I [used test-driven development][14] to create StringMatch (you can [check out the tests][15]), and I&#8217;m really glad that I did. As I was working out the algorithm, I was able to keep iterating to improve it with the confidence that previous cases that worked well were continuing to work well.

## Speed

On the one hand, we&#8217;re just matching up characters. But, as you can tell from the preceding sections, we&#8217;re doing _a lot_ of character comparisons. We keep trying to fit the query string into the subject string in different ways until we find the one that fits best. Luckily, computers are fast and JavaScript just-in-time compilers are pretty good, so this code has generally performed well enough for now.

At this point, we&#8217;ve only picked up the low hanging fruit in making StringMatch performance better. In profiling, I found that `_findSpecialCharacters` was taking around 8% of the total time when searching normally and that only needs to run once per string that we&#8217;re testing against, rather than for each character typed, making it easy to cache during the lifetime of a search.

Another simple optimization we&#8217;ve implemented takes advantage of the fact that items are eliminated as possible matches as the user types. As long as the user is adding more characters to the query, anything that didn&#8217;t match previously is not going to be a match now and we don&#8217;t even need to check.

The `StringMatcher` class implements these optimizations in a neatly compartmentalized way. Brackets creates a `StringMatcher` for a single query and throws it away at the end, so that it does not need to worry about stale caches.

## StringMatch all the things!

StringMatch is also used in Brackets&#8217; Go To Definition feature (which finds functions in your JavaScript files, for example). StringMatch is better than regex and substring searching when you&#8217;ve got an idea of the structure of the string being searched and what the users will expect the results to look like.

Brackets is open source! Have ideas on how to improve StringMatch or anything else? [Join in the fun!][1]

(Special thanks to Peter Flynn for a very thorough review of the StringMatch code which resulted in a good deal of cleanup in both the code and algorithm. Thanks also to Randy Edmunds for providing feedback on the first draft of this post.)

 [1]: http://brackets.io/
 [2]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js
 [3]: http://www.blueskyonmars.com/images/2013/03/StringMatch_in_Action.png
 [4]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js#L663
 [5]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js#L63
 [6]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js#L429
 [7]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js#L384
 [8]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js#L138
 [9]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js#L243
 [10]: http://en.wikipedia.org/wiki/Dynamic_programming
 [11]: http://en.wikipedia.org/wiki/Longest_common_substring_problem
 [12]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js#L271
 [13]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/src/utils/StringMatch.js#L475
 [14]: http://www.blueskyonmars.com/2013/01/02/test-driving-brackets/
 [15]: https://github.com/adobe/brackets/blob/2c1616a6346dfee29a8321b5ecc9e0f636ec42d8/test/spec/StringMatch-test.js