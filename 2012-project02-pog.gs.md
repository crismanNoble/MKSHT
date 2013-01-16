Title: Project 2: pog.gs
Abstract: Your very own, fully customizable, digital pog.
Date: 2012-04-21
Author: Cris Noble
Slug: pog.gs
Tags: learn, javascript, github, play, fiddle
Category: speed project

<a href="http://www.flickr.com/photos/freshfauxx/2494225600/" target="_blank" title="Pog! by freshfauxx, on Flickr">
<div id="panel" style="position:relative; background:red; width:560px; height:120px; background: transparent url(http://farm3.staticflickr.com/2015/2494225600_bce4851467.jpg) 0px -250px no-repeat; background-size: cover"></div>
</a>

When someone mentions "[pogs](http://en.wikipedia.org/wiki/Pogs "Pogs on Wikipedia")", my eyes light up and a pleasant feeling emerges from deep within the recesses of my brain. I miss pogs and the simplicity of gradeschool. I was playing around with bootstrap and brushing up on jquery (I would be lying if I told you I didn't get inspiration / view source on [Mig Reyes' footer image](http://migreyes.com/#footer-inquiries "Mig is cool")) so I whipped up this fun attempt to turn any image into a digital representation of a pog like object.

Enjoy.

###Give it a try
<iframe style="width: 100%; height: 375px" src="http://jsfiddle.net/crismanNoble/ujUa8/embedded/result" allowfullscreen="allowfullscreen" frameborder="0"></iframe>


[Play with the standalone demo](http://crismannoble.github.com/pog.gs/ "pog.gs demo page").  
[Fork out the repo](https://github.com/crismanNoble/pog.gs "pog.gs on github").  
[Tweak the jsfiddle](http://jsfiddle.net/crismanNoble/ujUa8/light/ "pog.gs fiddle").  

###Relevant Code
#####CSS to transform an image to a pog:

    :::css
    .pog {
        /*make div, give it a border radius of half the height*/
        height: 200px;
        width: 200px;
        border-radius: 100px;
        border: 3px solid black;  
        float: left;
        margin: 10px;
        
        /*give it some shadow for fun*/
        -webkit-box-shadow: 2px -3px 5px rgba(50, 50, 50, 0.75);
        -moz-box-shadow: 2px -3px 5px rgba(50, 50, 50, 0.75);
        box-shadow: 2px -3px 5px rgba(50, 50, 50, 0.75);
    }
    
    #pogFront {
    /*give the div a background image, center, cover */
        background: url('http://octodex.github.com/images/octonaut.jpg') center center;
        background-size: cover;
    }

More on background image properties from [Chris Coyier](http://css-tricks.com/perfect-full-page-background-image/ "CSS-Tricks: Perfect Full Page Background Image").
#####Function to change the image:

    :::javascript
    $(document).ready(function(){
      //Wait for a click on the button
      $('#go').click(function() {
        //grab the string the user put in the input box
	    var newImage = $('#newImage').val();
	    //and make that string the new source for the background of the front of the pog
        $('#pogFront').css('background-image','url(' + newImage + ')');
      });
    });
    
###Reward Beer
[Port Brewing Company: Hot Rocks Lager](http://www.portbrewing.com/our-beers/hot-rocks/ "Port Brewing Company: Hot Rocks Lager)

###Roadmap _(if I had no job)_
*   Allow for different options on the back
*   Create a bookmarklet
*   Allow for exporting
*   Pull image from URI (easier to share links)

_If you think these changes would be worth the time, fork the [project on github](https://github.com/crismanNoble/pog.gs) and let me know._

###Credits
Top Image Credit: [Pog! by freshfauxx, on Flickr](http://www.flickr.com/photos/freshfauxx/2494225600/ "Pog! by freshfauxx, on Flickr")  
Pog Front Base Image: [Octonaut by Cameron McEfee](http://octodex.github.com/octonaut/ "Octonaut by Cameron McEfee")

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>