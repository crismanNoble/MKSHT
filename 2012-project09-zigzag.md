Title: Project 9: ZigZag
Abstract: A fresh take on the layout of a ranked grid.
Date: 2012-05-15
Author: Cris Noble
Slug: zigzag
Tags: learn, d3.js, github, data vizualization, heatmap, grid
Category: speed project

*TLDR: I made [this](http://crismanNoble.github.com/zigzag) because I wanted an excuse to make a heatmap using d3.js.*

###Idea
I saw an awesome [heatmap](http://flowingdata.com/2012/04/11/how-recruiters-look-at-your-resume/) of how a recuiter looks at your resume that was created with eye tracking software.

It got me thinking. When we layout a grid showing ranked content, say top music albums, we use your standard left-to-right, top to bottom layout. 

![Standard](http://dl.dropbox.com/u/3898025/ltr.png)

But our eyes gravitate towards the top left, shouldn't the best content be closest to the top left? We could sort it by distance, but that seems odd too.

![Distance](http://dl.dropbox.com/u/3898025/dist.png)

So let's combine them and call it a ZigZag layout. I propose a new standard.

![ZigZag](http://dl.dropbox.com/u/3898025/zig.png)

[Check out the project demo page](http://crismanNoble.github.com/zigzag).

###Process
This gave me an excuse to play with [D3.js](https://github.com/mbostock/d3/wiki/Tutorials), and that is the main reason I tried it out. The crux of the entire visualization is this:

		:::javascript
		for (var j = 0; j<7; j++) {
			for(var i = 0; i < 5; i++) {
			distance.append("svg:rect").
			  attr("x", i*25).
			  attr("y", 25*j).
			  attr("height", 25).
			  attr("fill", "rgba(153, 0, 13, " + (100-3*man[i+j*5])/100 + ")").
			  attr("width", 25);
			};
		};

Which creates 7 rows of 5 squares, and varies the color opacity from 1 to 0 based on the given rank of each cell.

Feel free to browse the code in it's entirity over at [github](https://github.com/crismanNoble/zigzag).

###Road Map *(if I had no job)*

*    Allow for variation in grid size
*    Start the standard pattern after the fold
*    Create plugin to work with a masonry layout

###Reward Beer
[Southern Tier Brewing Company: Imperial Iniquity](http://www.stbcbeer.com/stbc/our-beers/year-round-2/year-round-imperials/iniquity-beer-page/)

*Do you think a left-to-right, top-to-bottm grid layout is best? Let's debate in the comments.*

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>