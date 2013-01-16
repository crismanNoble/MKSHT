Title: Project 4: Bill of Bytes
Abstract: The Bill of Rights, in a machine readable format.
Date: 2012-04-29
Author: Cris Noble
Slug: bill-of-bytes
Tags: learn, qr code, github, project gutenberg, open knowledge, creative commons
Category: speed project

*TLDR: I made [this](http://crismannoble.github.com/Bill-Of-Bytes/) while thinking of useful ways of using QR codes.*

![Article One](http://crismannoble.github.com/Bill-Of-Bytes/article1.png)

###Backstory
I was asked if it was possible to read the real Bill of Rights without visiting DC. I found them on Project Gutenberg and decided to make them into digital artifacts. I made this while learning javscript, exerimenting with QR codes, finding out you could host microsites on dropbox (since moved to github pages), learning a bit about Creative Commons while tinkering with GIMP.

###Let's Do It.
Step 1: Find the Bill of Rights via [Project Gutenberg](http://www.gutenberg.org/dirs/etext90/bill11h.htm).  
Step 2: Create a QR code for each Bill with [this handy tool](http://www.the2dcode.com/qr-code-generator).  
Step 3: Add a bit of color and utilize error correction to overlay some text.  
Step 4: Make a [demo page](http://crismannoble.github.com/Bill-Of-Bytes/) showing all of the Bills.  

###Relevant Code
This is the code that replaces the picture of the QR code so you don't have to reload the page.

	:::javascript
	function movepic(img_name,img_src) {
		document[img_name].src=img_src;
	}

Which works nicely, as long as your link tags look something like this:

	:::html
	<a href="#" onclick="movepic('activeBill','article1.png')">Article I</a>

Which is probably not the best way of doing it, but I am learning as I go. If there is a better way to do it, please say so in the comments.

###Reward Beer
[Stone Brewing Co: Arrogant Bastard Ale](http://www.arrogantbastard.com/arrogantbastard/default.asp)

###Road Map *(if I had no job)*

*    Make it responsive
*    Clean up the design
*    Turn it into large format posters to plaster around town

*If you think these are worth the time or effort, let me know in the comments or [fork the project on github](https://github.com/crismanNoble/Bill-Of-Bytes).*

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>