Title: Project 13: Knockout Text in CSS
Abstract: Because everything looks better with a little space.
Date: 2012-09-15
Author: Cris Noble
Slug: knockout
Tags: learn, css, space, html, fun
Category: speed project

![knocked out](https://dl.dropbox.com/u/3898025/mksht%20images/knockout.png)  

*TLDR: [I made some knockout-ish text using css](http://codepen.io/crismanNoble/full/bGzqu) because I like spacey text.*

###Background
My [wife](http://angelanoble.com) created [this sweet logo](http://ryangriffinvideo.com/images/logo.png) using a sort of knockout effect, but she used photoshop. As a front-end developer, I try to see if I can make cool shit with just css, so let's give it a go.

###Solution

You need a div:
	
	:::html
    <div class="knockout">Hai some text?</div>

And this is the key css:

	:::css
    .knockout {
        background: url(http://apod.nasa.gov/apod/image/0603/coma_misti.jpg) -80px -80px;
        -webkit-text-fill-color: transparent;
        -webkit-background-clip: text;
        font-weight: bold;
        font-size: 100px;
        font-family: arial, helvetica;
    }

That was easy! 

Some things to consider:

*   This should not be used in production **because it only works in webkit browsers.**
*   Make sure you use a big bold text.
*   Don't forget to play with your background image positioning!
*   If you like space, I recommend NASA's [APOD](http://apod.nasa.gov/apod/astropix.html)!
    
###Boom Goes the Dynamite
[See it in action](http://codepen.io/crismanNoble/full/bGzqu), or [view the source](http://codepen.io/crismanNoble/pen/bGzqu). **Don't forget you need to be in a webkit browser!**


###Reward Beer
[Goose Island: Demolition](http://www.gooseisland.com/pages/demolition/92.php)

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>