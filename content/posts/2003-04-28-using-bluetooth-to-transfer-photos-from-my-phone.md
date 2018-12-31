---
title: Using Bluetooth to transfer photos from my phone
author: Kevin Dangoor
type: post
date: 2003-04-28T18:03:57+00:00
url: /2003/04/28/using-bluetooth-to-transfer-photos-from-my-phone/
categories:
  - Technology

---
[Sony Ericsson : Accessories : download my pictures from T68i by bluetooth @ Esato][1] &#8211; I was wondering if there was a way to usefully use my phone&#8217;s digital camera. Apparently, with Bluetooth there is!

Here&#8217;s an important part of the tip:

> Most of these Bluetooth Adapters use the WIDCOMM drivers/software.
> 
> So to enable sending images FROM your phone TO your pc over Bluetooth, firstly MAKE SURE you have the very latest software for your adapter. Then open regedit.exe and do the following:
> 
> Navigate to HKEY\_CURRENT\_USER\Software\Widcomm\BTConfig\Services
  
> Here there is a list of profiles supported by your PC
  
> Find the one for &#8216;Infomation Exchange&#8217;
  
> Do this by looking in each folder.
  
> For me, there were folders 0001 to 0007, and the one I was after was 0004. (You can tell because there is a value called &#8216;Name&#8217;, with data &#8216;Information Exchange&#8217;)
  
> In this key, change the DWORD string &#8216;AcceptOther&#8217; to hex value 1 &#8211; it is 0 by default.
  
> Close regedit
> 
> ENJOY !

 [1]: http://www.esato.com/board/viewtopic.php?topic=9559&forum=15#post119923 "Sony Ericsson : Accessories : download my pictures from T68i by bluetooth @ Esato"