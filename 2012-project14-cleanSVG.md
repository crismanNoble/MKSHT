Title: Project 14: Extracting SVGs From The Noun Project
Abstract: Keep the code, lose the clutter.
Date: 2012-12-01
Author: Cris Noble
Slug: cleanSVG
Tags: learn, svg, jQuery, fun, tool, library, scraping data.
Category: speed project
Status: Draft
![SVG code](http://dl.dropbox.com/u/3898025/npdownload)

*TLDR: I outlined a process to [move verbose SVG code out of my html document](http://cleanSVG.crisnoble.com/) beause I was starting to lose my sanity.*

###Background
I use [The Noun Project](http://thenounproject.com) all the time. I love the icons, I love that they are svg, but I hate that download button. What if you just want to embed the svg onto your webpage directly? You think I'm going to download a .zip, uppack it, open it up in a text editor and copy the code into my html? Hell no, I'm going to right click, inspect element and copy as html saving their bandwidth and my time. When you use as many of their icons as I do, you need an even faster way to grab the svg code.

###Step 1: Identify your target
I had heard the word `curl` in some data scraping sites, but never tried it. Two seconds of googling later I had a PHP script that was spitting out the html code of any webpage.

	:::php
    <?php
    $ch = curl_init();

	// set URL and other appropriate options
	curl_setopt($ch, CURLOPT_URL, $url);
	curl_setopt($ch, CURLOPT_HEADER, 0);
	curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

	//grab entire HTML document and store it for manipulation
	$output = curl_exec($ch);
	
	//close curl resource, and free up system resources
	curl_close($ch);
	
	echo $output;
	
    ?>

But now I have a huge mess of HTML, and I only want one piece of it.
![](http://dl.dropbox.com/u/3898025/npTarget)
As you can see the svg code is inside of a `li` element with the `id="big-###"` surrounded by other icons of the same noun. In order to target the correct noun we need to trim the `$url` variable to find what icon we want.

	<?php
	:::php
	$symbolID = substr($url,$symStartPos,strlen($url));
	$symStartPos = strpos($url, '#icon-No')+strlen('#icon-No');
	$symbolID = substr($url,$symStartPos,strlen($url));
	?>
	
	
###Step 2: Extract the code
I started by trying to do a REGEX to target everything between the correct div, but in the end I did a crazy 3 part string search function. It seems insane but to me it was easier than dealing with REGEX, one day I will understand them.

	:::php
	<?php
	$output = curl_exec($ch);

	$svgT1StrStart = '<ul class="big">';
	$svgT1StrEnd = '<!--end column -->';
	$svgT1PosStart = strpos($output, $svgT1StrStart)+strlen($svgT1StrStart);
	$svgT1PosEnd = strpos($output, $svgT1StrEnd);
	$svgT1 = substr($output, $svgT1PosStart, $svgT1PosEnd-$svgT1PosStart );

	$svgT2StrStart = '<li id="big-'.$symbolID.'">';
	$svgT2PosStart = strpos($svgT1, $svgT2StrStart)+strlen($svgT2StrStart);
	$svgT2PosEnd = strlen($svgT1);
	$svgT2 = substr($svgT1, $svgT2PosStart, $svgT2PosEnd-$svgT2PosStart );

	$svgT3StrEnd = '</li>';
	$svgT3PosStart = 0;
	$svgT3PosEnd = strpos($svgT2, $svgT3StrEnd);
	$svgT3 = substr($svgT2, $svgT3PosStart, $svgT3PosEnd-$svgT3PosStart);

	$svg = trim($svgT3);
	
	?>



###Step 3: Do AJAX
All that is left is to dynamically pass a target URL to the script and have it spit back the result. I am cheating and using jQuery, here is the gist of the call.

	:::javascript
    $("#submit").click(function() {

        var url = encodeURIComponent($('#urlInput').val());

        var dataString = 'url=' + url;

        $.ajax({  
          type: "GET",  
          url: "php/curl.php",  
          data: dataString,  
          success: function(data) {  
            var datas = data.split("SPLITTA");
            $('#attributionCode').html("<textarea>"+datas[0]+"</textarea>");
            $('#attribution').html(datas[1]);
            $('#svgCode').html("<textarea>"+datas[2]+"</textarea>");
            $('#svg').html(datas[3]);
          }
        });  
        return false;
    });

You may have noticed my ridiculus `data.split` call, it is a total hack to split up the attibution data, code, svg data and svg code. I should probably use a [JSON object](http://php.net/manual/en/book.json.php) but I was rushing. 

This is the piece of PHP to recieve the url, pass it to the extraction function, and return the value back to the webpage.  

	:::php
    <?php
    //URL of targeted site
    $url = $_GET['url']; 

    …
    //bunch of processing of curl output
    …
    
    //echo the code of attribution:
    echo htmlentities($attribution);
    echo "SPLITTA";
    //echo the attribution
    echo $attribution;
    echo "SPLITTA";
    //echo code of svg
    echo htmlentities($svg);
    echo "SPLITTA";
    //echo svg itself for display
    echo $svg;
    
    ?>
    
###Step 4: Clean it up
For this project I decided to try out the amazing [Foundation Framework](http://foundation.zurb.com/) from [Zurb](http://www.zurb.com/), it was super easy to get going. To format the svg code I used the nice and easy [Prism.js](http://prismjs.com/). I added attribution information as well in the final hour. 

Screen shot of the final product:
![np2svg](http://dl.dropbox.com/u/3898025/np2svgSS)

[See it in action](http://crisnoble.com/np2svg), or [view the source](https://github.com/crismanNoble/np2svg).

###Roadmap *(if I had no job)*
*   Multiple Symbols
*   Lookup with work, id **or** rul
*   Handle lack of *http://* properly
*   Adjustable dimensions
*   Clean the extracted code a bit
*   Grab noun via url argument
*   Auto copy to Clipboard
*   Pick a good name

###Reward Beer
[Stone Brewing Co: Sublimely Self-Fighteous](http://www.stonebrew.com/sublimely/)

###Final Word
**Dear theNounProject,**  
I love you and everything you stand for. If this project is a violation of your TOS, please tell me and I will take it down.  
Love,  
Cris Noble


**Everyone Else**  
I don't think this was the best way of doing pretty much any of what was done, it was a quick hack but I want to learn, suggestions to clean up the code are more than welcome. Also any good REGEX tutorials?  
Thanks,  
Cris

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>