Title: Project 7: Taste The Rainbow
Abstract: A delicious rollover experiment.
Date: 2012-05-07
Author: Cris Noble
Slug: tasteTheRainbow
Tags: javascript, jsfiddle, jquery, animation, svg, the noun project, play, css animation
Category: speed project

*TLDR: I made [this](http://jsfiddle.net/crismanNoble/8F7yD/embedded/result/) because I was bored.*

###Challenge
I love the noun project, especially since all of their icons are liscenced under either public domain or creative commons. I wanted to give them some color, preferably a different random one on each rollover, so I started to fiddle about. In the process I learned a little bit about SVGs and jQuery.

[Demo](http://jsfiddle.net/crismanNoble/8F7yD/embedded/result/)  
[Fiddle](http://jsfiddle.net/crismanNoble/8F7yD/)

###How To
First we need a color pallet do deal with, how about [this one](http://www.colourlovers.com/palette/1338021/Original_Skittles), based on skittles? Yummy. Let's turn it into an array.

	:::javascript
	var colors = ["#6F216C", "#F34B0D", "#C50102", "#5DA537", "#F1D81B"];

We need some svg icon's too, let's head over to [the noun project](http://thenounproject.com/) and pick [one](http://thenounproject.com/noun/globe/#icon-No711).

You probably already know this, but any svg is just code which defines the fill and the path's. The cool thing about the noun project is they require zero width paths, meaning it is all fill all the time. The point is we can access the 'color' of the svg icon with the css attibute fill. By giving the icons classes, we can really play with it using jquery.

Example SVG code copied from theNounProject *(inspect element -> copy as html -> paste)*

	:::html
	<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="400px" height="400px" viewBox="0 0 79.048 100" enable-background="new 0 0 79.048 100" space="preserve">
		<path d="M74.654,77.027l-3.905-6.764c-1.341,1.238-2.793,2.352-4.299,3.389l-1.89-3.273c8.75-6.106,14.488-16.232,14.488-27.715
			c0-18.663-15.129-33.793-33.794-33.793c-5.136,0-9.985,1.18-14.343,3.229l-1.93-3.342c1.637-0.789,3.331-1.477,5.087-2.025L30.182,0
			C12.618,6.223,0,22.994,0,42.664C0,66.655,18.77,86.338,42.393,87.82v2.532c-6.455,1.266-21.45,4.751-20.429,9.647h46.622
			c0.396-4.973-14.176-8.404-20.474-9.651v-2.558C58.208,87.154,67.419,83.226,74.654,77.027z M7.625,42.664
			c0-12.878,6.515-24.249,16.409-31.036l1.917,3.321c-8.752,6.106-14.491,16.235-14.491,27.715c0,18.665,15.13,33.796,33.793,33.796
			c5.137,0,9.987-1.181,14.346-3.23l1.91,3.307c-4.923,2.387-10.427,3.759-16.258,3.759C24.506,80.295,7.625,63.412,7.625,42.664z"></path>
	</svg>

Let's clean it up, *give it a class*, and give it a meaningful id, I usually comment out where I found it too.

	:::html
	<!--globe icon http://thenounproject.com/noun/globe/#icon-No711 -->
	<svg id="globe" viewBox="0 0 79.048 100" enable-background="new 0 0 79.048 100" class="icon">
		<path d="M74.654,77.027l-3.905-6.764c-1.341,1.238-2.793,2.352-4.299,3.389l-1.89-3.273c8.75-6.106,14.488-16.232,14.488-27.715
		    c0-18.663-15.129-33.793-33.794-33.793c-5.136,0-9.985,1.18-14.343,3.229l-1.93-3.342c1.637-0.789,3.331-1.477,5.087-2.025L30.182,0
		    C12.618,6.223,0,22.994,0,42.664C0,66.655,18.77,86.338,42.393,87.82v2.532c-6.455,1.266-21.45,4.751-20.429,9.647h46.622
		    c0.396-4.973-14.176-8.404-20.474-9.651v-2.558C58.208,87.154,67.419,83.226,74.654,77.027z M7.625,42.664
		    c0-12.878,6.515-24.249,16.409-31.036l1.917,3.321c-8.752,6.106-14.491,16.235-14.491,27.715c0,18.665,15.13,33.796,33.793,33.796
		    c5.137,0,9.987-1.181,14.346-3.23l1.91,3.307c-4.923,2.387-10.427,3.759-16.258,3.759C24.506,80.295,7.625,63.412,7.625,42.664z"></path>
	</svg>​

Now we can style it with some CSS: *[follow with the fiddle](http://jsfiddle.net/crismanNoble/8F7yD/2/).*

	.icon {
	    width: 50px;
	    height: 50px;
	}

	.icon:hover {
	    fill: #6F216C;
	}

<iframe style="width: 560px; height: 150px" src="http://jsfiddle.net/crismanNoble/8F7yD/2/embedded/result/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

But what if we want to radomize the hover color? Let's make a quick function that will pick a random color from the colors array.

	:::javascript
	function colorize() {
		return colors[Math.floor(Math.random()*colors.length)]
	};

Okay cool, now let's color in an icon each time we rollover it. If we give the svg a '.rollover' class, we can use jquery to give it a random color on rollover and change it back to black when we mouseout. *[follow with the fiddle](http://jsfiddle.net/crismanNoble/8F7yD/3/).*

	:::javascript
	$('.rollover').hover(
		function() {
			$(this).css('fill', colorize());
			},
		function() {
			$(this).css('fill', 'black');
			});

<iframe style="width: 560px; height: 150px" src="http://jsfiddle.net/crismanNoble/8F7yD/3/embedded/result/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

Let's say we want the new rollover color to stick, just give the icon a different class, say '.colorStick' and write a new function.

	:::javascript
	$('.colorStick').hover(
		function() {
			$(this).css('fill', colorize());
			},
		function() {
			//do nothing on mouseout.
			});

If we want to give an icon a random color on loading of the page, by using [.each()]() we can fill all the '.colorStart' icons in. 

	:::javascript
    $('.colorStart').each(function() {
        $(this).css('fill', colorize());
    	});

If we want to be able to start with any fill, provide a random rollover color, and then return that fill, we need to tweak the rollover function just a bit to save the color of the icon pre-rollover. *[follow with the fiddle](http://jsfiddle.net/crismanNoble/8F7yD/4/).*

	:::javascript
	var saveColor;
	$('.rollover').hover(
		function() {
			saveColor = $(this).css('fill');
			$(this).css('fill', colorize());
			},
		function() {
			$(this).css('fill', saveColor);
			});

<iframe style="width: 560px; height: 300px" src="http://jsfiddle.net/crismanNoble/8F7yD/4/embedded/result/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

###Further Reading

*    jQuery [.hover()](http://api.jquery.com/hover/) vs. [.mouseover()](http://api.jquery.com/mouseover/)
*    [jQuery.each()](http://api.jquery.com/jQuery.each/)
*    [.css()](http://api.jquery.com/css/)

###Road Map *(if I had no job)*

*    Integrate Raphael.js 
*    Clean up the code by hosting the svgs in a separate file
*    Perform the transitions with css animations
*    Create a jQuery plugin, not because it is very functional, but to learn how to create a jQuery plugin.

###Reward Beer
[Goose Island: Pepe Nero](http://www.gooseisland.com/pages/pepe_nero/194.php)  
*Open invitation to Goose Island: I will redesign your website in exchange for free beer, you kind of need it, and I really like your beers.*

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>