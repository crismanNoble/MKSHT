Title: Project 10: Penrose in CSS
Abstract: Recreation of the famous tribar in CSS.
Date: 2012-08-01
Author: Cris Noble
Slug: penrose
Tags: learn, math, geometry, isometric, penrose, css, art
Category: speed project

![Penrose Triangle](http://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/Penrose-dreieck.svg/526px-Penrose-dreieck.svg.png)  

*TLDR: [I made a penrose triangle in css](http://crismanNoble.github.com/penroseCSS) because geometry is neat.*

###Background
I used to attempt to draw penrose triangles during class, and would always sketch out a contorted mess. Then I learned geometry. If you think of a penrose triangle as a series of smaller triangles you begin to see that it is nothing more than craftily shaded [equilateral triangles](http://www.wolframalpha.com/input/?i=triangle+graph&lk=1&a=ClashPrefs_*Graph.TriangleGraph-) next to each other. 

Now that we know the secret to the penrose triangle we need to translate these learnings into CSS.
###Get To It
We can make a CSS triangle of pretty much any shape using [this old trick](http://davidwalsh.name/css-triangles).

A perfectly equilateral triangle would have the following properties: 2 units wide, sqrt(3) units high.

That can be approximated with this css:  

	:::css
    .triangle {
      width: 0px; 
      height: 0px; 
      border-left: 10px solid transparent;
      border-right: 10px solid transparent;
      border-bottom: 17.25px solid red;
    }

You need to flip everyother triangle too:
	
	:::css
    .triangleOdd {
      width: 0px; 
      height: 0px; 
      border-left: 10px solid transparent;
      border-right: 10px solid transparent;
      border-top: 17.25px solid blue;
    }

Put triangles next to each other with the following rules

    :::css
    margin-left: -10px;
    float: left;

Keep stacking your triagles left, your going to need 11 per row, and six rows in total. Put everything in a wrapper that is 120px wide and bam, your done.  

[See it in action](http://crismanNoble.github.com/penroseCSS), or [view the source](https://github.com/crismanNoble/penroseCSS).


###Reward Beer
[Samuel Smith's Brewery: India Ale](http://www.samuelsmithsbrewery.co.uk/indiaale.html)

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>