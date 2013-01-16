Title: Project 3: Tufte in D3
Abstract: Recreating Tufte's 2004 MLB Season Graph
Date: 2012-04-25
Author: Cris Noble
Slug: tufte-in-d3
Tags: learn, d3.js, github, data vizualization, field notes, new skill, rickshaw, data
Category: speed project

![Tufte](http://dl.dropbox.com/u/3898025/TufteRealScale.png)

*TLDR: I made [this](http://crismannoble.github.com/Tufte-in-D3/) while learning about [D3.js](http://d3js.org/).*

###Challenge
I wanted to re-create a graph by my favorite information designer with the library from my favorite coder.

>You know Hunter S. Thompson typed 'The Great Gatsby'? He'd look at each page Fitzgerald wrote, and he copied it. The entire book. And more than once. Because he wanted to know what it felt like to write a masterpiece. He was so hungry, yeah. Innocent, and yearning. -Johnny Depp

I chose [this one](http://dl.dropbox.com/u/3898025/TufteReal.png) from [The Visual Display of Quantitative Information](http://www.edwardtufte.com/tufte/books_vdqi).

###Data Gathering
There are probably much better ways to do this, but I used [Espn.com's season results](http://espn.go.com/mlb/team/schedule/_/name/SEA/year/2004/seasontype/2/half/1/) and Google Docs' `=ImportHtml()` function to compile the results of the 2004 MLB season for each team.

###Making the Graph
Since I am using [Rickshaw](http://code.shutterstock.com/rickshaw/) I am going to need to convert my dates into the number of seconds since the linux epoch. This fuction helped me a lot `=(A2-25569)*86400`, where `A2` is a standard date, for example `3/30/2012`.

In order to create the X and Y values I had to format the data like so:

`{ x: 1080604800 , y: -1 }, { x: 1080691200 , y: 0 } ...  { x: 1096588800 , y: 40 }, { x: 1096675200 , y: 39 }, { x: 1096761600 , y: 40 }`

Nothing a little `=E2&" { x: "&C3&" , y: "&D3&" },"` dragged down an entire column can't handle, just use the last row for your query.

In Rickshaw it is pretty easy to make a simle graph, see [this file](https://github.com/crismanNoble/Tufte-in-D3/blob/master/js/custom.js) for how I did it.

###Final Result
I think I am pretty close to a replication of the original, you be the judge.

![my version](http://dl.dropbox.com/u/3898025/Screenshot.png)

[Check out the original](http://dl.dropbox.com/u/3898025/TufteReal.png).  
[Check out the demo](http://crismannoble.github.com/Tufte-in-D3/).  
[Fork the Repo](https://github.com/crismanNoble/Tufte-in-D3).  

>Those look great! Nice job.*-Mike Bostock*


###Reward Beer
[Lagunitas: Wilco Tango Foxtrot Ale](http://www.lagunitas.com/beers/index.html)

###Road Map

*    Use [tabletop.js](https://github.com/jsoma/tabletop) to import the data live from the google doc.
*    Determine why Tufte was not consistant with his color schemes.
*    Add a level interactivity to these charts.
*    Keep making cool stuff in D3.

*Do you have a favorite Tufte chart / graph that you want to make with D3?*

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>