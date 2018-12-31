---
title: Finding a user’s Documents folder on Windows and Mac
author: Kevin Dangoor
type: post
date: 2005-08-05T14:27:23+00:00
url: /2005/08/05/finding-a-users-my-documents-folder-on-windows/
categories:
  - Python

---
**Update:** I revised this to include the Mac way of finding the user&#8217;s documents directory. Perhaps the Python standard library should include a way to get at the best path for storing documents.

## For Windows

Yuck. Coming within 10 feet of win32 programming, you can really appreciate the need for .NET and a sane API.

For anyone needing to find the user&#8217;s &#8220;My Documents&#8221; folder on Windows with Python, here is one way that I&#8217;ve found to work based on [this MSDN article][1]. (As awful as the API is, I will say that MSDN is a great resource!)

<pre>from win32com.shell import shell
df = shell.SHGetDesktopFolder()
pidl = df.ParseDisplayName(0, None,  
    "::{450d8fba-ad25-11d0-98a8-0800361b1103}")[1]
mydocs = shell.SHGetPathFromIDList(pidl)
</pre>

I really wanted to use shell.SHGetFolderPath but I couldn&#8217;t get a combination that works for retrieving &#8220;My Documents&#8221;. In order to get My Documents from there, you need a PyHandle for the user, and I got the method above working before I found my handle&#8230; You can get &#8220;My Pictures&#8221; easily from shell.SHGetFolderPath, however.

<pre>from win32com import shell, shellcon
mypict = shell.SHGetFolderPath(0, shellcon.CSIDL_MYPICTURES, 0, 0)
</pre>

I&#8217;m sure that if you do win32 programming all the time, you get used to this stuff. Knowing that doesn&#8217;t make me feel less sorry for the folks that are doing win32 programming.

## For The Mac

The Mac (Carbon) way of doing this is similar to the SHGetFolderPath call on Windows. Both of these APIs make more sense than the one I went with (ParseDisplayName with that lovely GUID).

<pre>from Carbon import Folder, Folders
folderref = Folder.FSFindFolder(Folders.kUserDomain, 
    Folders.kDocumentsFolderType, False)
docs = folderref.as_pathname()
</pre>

 [1]: http://msdn.microsoft.com/library/default.asp?url=/library/en-us/shellcc/platform/shell/programmersguide/shell_basics/shell_basics_programming/manage.asp