Title: Project 8: Impulse
Abstract: Every project starts with an impulse.
Date: 2012-05-11
Author: Cris Noble
Slug: impulse
Tags: html, css, javascript, github, boilerplate, impulse
Category: speed project

>In classical mechanics, an impulse (abbreviated I or J) is defined as the integral of a force with respect to time.

*TLDR: I made **[impulse](https://github.com/crismanNoble/impulse)** because despite the great boilerplates out there, I always spend too much time setting up my files when making a demo.*

>I want the minimum setup for a nerdy show and tell.

###Problem
I spend a lot of time in [jsfiddle](http://jsfiddle.net) creating experiments. If my experiment ever becomes worthy of a demo page, I find I spend way too much time just creating the proper directory structure, linking to my stylesheets in the head, and visiting [this page](http://docs.jquery.com/How_jQuery_Works) to get the link to Google's CDN and remembering to do this `$(document).ready(function(){});`.  

**The bottom line is, I want to spend more time coding and less time tweaking my files and directory.**

Before you read any further you should know I have heard about the wonderful [html5boilerplate.com](http://html5boilerplate.com/). There are many other amazing resources out there [solving this exact problem](http://www.cibgraphics.com/projects/vanilla). However, I don't need IE6+ compatibility, mobile responsiveness, optimal javascript loading patterns, DNS prefecthing, or graceful degredation. Remember, this is for demo sites and proof of concepts only. I want the minimum setup time for a nerdy show and tell. I do not plan on using this on any kind of production site (nor should you).

###What to build:
This is going to be my file structure:  

	index.html  

	css/style.css  

	css/reset.css  

	js/custom.js  

	img/  

	favicon.ico  

	humans.txt  

###Solution
**index.html**  
*Dear God, I hate bookmarks with no favicons. Don't forget to link to jQuery, if that's your thing.*

	:::html
	<!doctype HTML>
	<html>
	<head>
	  <meta charset="utf-8">

	  <title>Impulse | Title Goes Here</title>

	  <meta name="description" content="This can be a longer description of what you are doing." />
	  <meta name="keywords" content="fun, short, sometimes two, word descriptions" />

	  <link rel="author" href="/humans.txt" />

	  <link rel="shortcut icon" href="favicon.ico" />

	  <link rel="stylesheet" href="css/style.css">
	  <link rel="stylesheet" href="css/reset.css">

	  <script src="//ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js" type="text/javascript"></script>
	  <script src="js/custom.js"></script>
	</head>
	<body>
		Please fill me in with wonderfully amazing content.
	</body>
	</html>


**css/style.css**  
*I think sans-serif is nicer than Times New Roman. If someone on a PC took the time to install Helvetica, I want them to see it.*

	:::css
	body {
		font-family: helvetica, arial, sans-serif;
	}

**css/reset.css**  
*This is a direct copy from [jsFiddle.net](http://jsfiddle.net/css/normalize.css) because I always leave the 'Normalized CSS' [button checked](http://markup.io/v/4f04azwfh11t).*

	:::css
	body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,form,fieldset,input,textarea,p,blockquote,th,td { 
		margin:0;
		padding:0;
	}
	table {
		border-collapse:collapse;
		border-spacing:0;
	}
	fieldset,img { 
		border:0;
	}
	address,caption,cite,code,dfn,em,strong,th,var {
		font-style:normal;
		font-weight:normal;
	}
	ol,ul {
		list-style:none;
	}
	caption,th {
		text-align:left;
	}
	h1,h2,h3,h4,h5,h6 {
		font-size:100%;
		font-weight:normal;
	}
	q:before,q:after {
		content:'';
	}
	abbr,acronym { border:0;}

**js/custom.js**  
*I use jQuery, but thanks to my jsFiddle crutches, I never remember this*

	:::javascript
	$(document).ready(function(){
  	// Do stuff onload
	});

**humans.txt**  
I like `humans.txt` it's like an even nerdier `README.md` that no one ever reads. Read more about humans.txt [here](http://humanstxt.org/).

	Hi there, I am a human; you must be too if you are reading this.

**favicon.ico**  

![penrose](http://crisnoble.com/images/penrose.png "penrose")  


That's it.

###Now what?
Now if I want to use this for my next `crazyProjectIdea` I just fire up the old terminal.

	:::bash
	git clone git@github.com:crismanNoble/impulse.git crazyProjectIdea
	rm -rf .git
	git init crazyProjectIdea

If you don't know about git you should [learn it](http://git.or.cz/course/)! Until then you can download all of the files at once with this [.zip file](https://github.com/crismanNoble/impulse/blob/master/impulse.zip?raw=true). If you don't know what a .zip file is, [contact me](http://crisnoble.com/sayhi). Seriously, I will help you.

###More Resources

*    [Vanilla5](http://www.cibgraphics.com/projects/vanilla)
*    [H5BP](http://html5boilerplate.com/)
*    [Eric Meyer's Reset.css](http://html5boilerplate.com/)
*    [html 9 Responsive Boiler Strap js](http://html9responsiveboilerstrapjs.com/)
*    [htmlshell](http://htmlshell.com/)

###Road Map

*    Create a lite and a robust version
*    Work in more css defaults, throw IE a bone.
*    Create a project page with configurable links to download

###Reward Beer
[Rouge: Morimoto Black Obi Soba Ale](http://www.rogue.com/beers/morimoto-black-obi-soba.php), delicious.

###The Name
Impulse refers to both the crazy idea that pops into my head and the way that this can speed up my demo time.

[From Wikipedia:](http://en.wikipedia.org/wiki/Impulse_(physics))
>Impulse is:  
	the gun powder accelerating the bullet in a rifle,  
	the bow string accelerating the arrow,  
	the rocket engines accelerating the shuttle,  
	the fist accelerating the punching bag.  

and now, getting a usable skeleton directory and files in three lines.

*I'd love to hear your workflow for demo projects; mine just got a whole lot easier, but it's not over. Feel free to [fork or follow the project on github](https://github.com/crismanNoble/impulse).*

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>