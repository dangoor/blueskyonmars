---
title: Quick and dirty hack to get syntax coloring in Keynote
author: Kevin Dangoor
type: post
date: 2008-09-11T15:27:37+00:00
url: /2008/09/11/quick-and-dirty-hack-to-get-syntax-coloring-in-keynote/
categories:
  - Python
  - Technology
tags:
  - keynote
  - mac os x

---
I figured I&#8217;d toss this out in the event that someone has a better solution in hand. I tossed this together quickly and it works. It requires that you have Pygments installed and pygmentize on your path (which is silly, because I could have just imported pygments as a libraryâ€¦) It also requires that Safari is running. But, hey, it works.

<pre>import os
import sys

def go():
    if len(sys.argv) != 2:
        print "Usage: %s &lt;filename&gt;" % sys.argv[0]
        sys.exit(1)
    output_fn, ext = os.path.splitext(sys.argv[1])
    output_fn += '.html'
    print "Generating %s" % (output_fn)
    os.system("pygmentize -O full -o %s %s" % (output_fn, sys.argv[1]))
    print "Copying to clipboard..."
    fullpath = os.path.abspath(output_fn)
    os.system("""osascript&lt;&lt;END
tell application "Safari"
        activate
        make new document at end of documents
        set url of document 1 to "file://%s"
end tell

tell application "System Events"
        tell process "Safari"
                click menu item "Select All" of menu "Edit" of menu bar 1
                click menu item "Copy" of menu "Edit" of menu bar 1
                click menu item "Close Window" of menu "File" of menu bar 1
        end tell
end tell
END
""" % (fullpath))
    
if __name__ == "__main__":
    go()
</pre>