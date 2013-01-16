Title: Project 12: Keep Watching
Abstract: You bet that I'm not the only one watching the Keep Watch Mixes.
Date: 2012-08-20
Author: Cris Noble
Slug: keepWatching
Tags: php, music, soundcloud, api, jQuery, css, html
Category: speed project

![Keep Watching](http://dl.dropbox.com/u/3898025/keepWatching.png)

*TLDR: I made [this](http://crisnoble.com/keepWatch/) because [this](http://mishkanyc.com/bloglin/category/keep-watch-mix/) is too tedious.*

###Challenge
I love MISHKA's Keep Watch Mixes, and have listened to every single one multiple times. It is boring and tedious to scan through [this page](http://mishkanyc.com/bloglin/category/keep-watch-mix/), and even though all the mixes [are on soundcloud now](http://soundcloud.com/bloglin), it remains a pain in my ass to listen to only the Keep Watch Mixes.

###Data Hoarding
I use [IFTTT](http://ifttt.com/recipes/52206) to alert me the second that a new mix is released. I then faithfully update a google spreadsheet when it drops. I always check discogs to make sure everything is up to date. Finally, I turn on the headphones and go for a long run.

###Output
First I'm going to need a database, So I put everything from my spreadsheet into mySQL.

Then I played with the soundcloud api and bastardized the default player into something I could tolerate.

The meat of the site is to pull data from your mySQL table you need something like this:

*Editor's note: I made this before learning about bacbone.js and I think I violated every MVC policy with the following but hey, I'm learning.*
	
	:::php
	<?php
	$query="SELECT * FROM mixInfo ORDER BY date DESC";
	$result=mysql_query($query);
	//count the number of rows
	$num=mysql_numrows($result);
	?>
	
Now cycle through the rows of the result and thow it into some html.

	:::php
	<?php
        $i=0;
        while ($i < $num) {
            $title=mysql_result($result,$i,"title");
            $release=mysql_result($result,$i,"release");
            $tracklist=mysql_result($result,$i,"tracklist");
            $artist=mysql_result($result,$i,"artist");
            $date=mysql_result($result,$i,"date");
            $fileSoundCloud=mysql_result($result,$i,"fileSoundCloud");
            $fileBlog=mysql_result($result,$i,"fileBlog");
            echo "<div class=\"slide\">";
            echo "<img src=\"images/coverimages/kw".$release.".jpg\"/>";
            echo "<div class=\"details\">";
            echo "<div class=\"topInfo\">";
            echo "<h1>".$title."</h1><br/>";
            echo "<h1>".$artist."</h1></div>";
            echo "<div class=\"moreInfo\">";
            echo "<a href=\"".$fileSoundCloud."\" target=\"_blank\">download";
            echo "<img src=\"images/soundcloud.png\" class=\"icon\"/></a></div>";
            echo "<div class=\"moreInfo\">tracklist";
            echo "<div class=\"tracklist\">".$tracklist."</div></div>";
            echo "<a href=\"".$fileSoundCloud."\" class=\"sc-player\"></a>";
            echo "</div></div>";
            $i++;
        }

        ?> 

You can browse the css, php, javascript and html over at [github](https://github.com/crismanNoble/keepWatching). If you want a more indepth writeup, let me know in the comments.

###Final Result
I am pretty happy with the output, it looks okay and is easy to keep updated.

>@Crisnoble cool shit man!*-[@MishkaNYC](https://twitter.com/#!/MishkaNYC/status/181776827759595521)*

*Dear MISHKA,  
If you hook me up with a free t-shirt I will manage your websites for life. MISHKA rocks, but goddamn you need to update your webdesign. You release cutting edge mixes by topnotch djs, heard by thousands, but you can't spend 10 minutes creating a microsite? [Give me a call](http://crisnoble.com/sayhi).*

###Road Map

*    Automate the updating
*    Open source everything so that anyone can make any discography

###Reward Beer
[3 Floyds Brewing: Artic Panzer Wolf](http://www.3floyds.com/our-beers-2/)

*What is your favoite mix series? Want to make it look pretty? [Let's get in touch](http://crinoble.com/sayhi)*
***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>