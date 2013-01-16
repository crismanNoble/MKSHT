Title: Project 1: Use a CMS
Abstract: Fieldnotes from my journey to find a simple CMS.
Date: 2012-04-19
Author: Cris Noble
Slug: cms
Tags: learn, cms, github, dropbox, google, html, css, markdown, wordrpess, calepin, ruby, octopress, jeykyll, ycombinator, hacker news, speedproject, field notes
Category: field notes

*TLDR: [Calepin.co](http://calepin.co) is perfect if you like the default template.*

###What is a CMS?
CMS stands for Content Mangement System. There are subtleties to the actual definition, so you should read the the [Wikipedia entry](http://en.wikipedia.org/wiki/Web_Content_Management_System). Funny, I had always thought that a content management system was another word for blog, but now I see why people build websites using Wordpress. There are [literally hundreds of options] out there so where does a wide eyed kid like me start? Well, to start with let's see what hacker news has to say [about](http://news.ycombinator.com/item?id=1925170) [it](http://news.ycombinator.com/item?id=3588227). Time to get my thinking cap on.

###Why do I care what a CMS is?
After attending an inspirational speech by Mig Reyes in Chicago, I was inspired to focus on creating things, trying things, just plain ole doing things. 
>Just make some shit. That's how you learn shit.  
>-Mig Reyes

I was hooked. I want to start dumping the crazy ideas out of my head and onto the internet. My plan is to complete 100 speed projects, put as many of them as possible on [github](https://github.com/crismanNoble), and learn a ton of new skills while I am at it. To encourage myself to actually get things moving, I will drink a delicious beer after each project. I could use my knowledge of handcrafted HTML and CSS to make individual pages for each project, but I would end up spending as much time updating my project log as actually making things. This is where a CMS can excel, it can eliminate the administrative mumbo jumbo and let you focus on content creation.

###What do I need?
Before I pick a product to use, I need to define my requirements.  

*    Although some think it is dead, I absolutely want **RSS support** out of the box.
*    I love the **simplicity** of [Svbtle](http://svbtle.com/), but will probably never be in their club.
*    I want to share the process of the things I make so I am probably going to need **code highlighting**.
*    Not that anyone will read this stuff, but I want a **comment system**.
*    I love using **google analytics**, even if we are talking 1 visit a day.  
*    If I ever make something the cool, I would like to know that it **could withstand the hackernews effect**.  
*    In case this project takes off, I want the ability to use a **custom domain**.  
*    I am usually on some kind of wifi, but it would be nice to have the **ability to write posts offline**.  
*    I am pretty cheap so it needs to be **free**.

###Contenders
I have narrowed my options down quite a bit. A final pro / con list:
**[Wordpress](http://wordpress.org)**  
*Pros*: Most commonly used CMS in the world, can handle a small blog, can create a full featured website. Quick setup, ability to self host everything. Lot's of plugins and themes. Built in analytics. Add 'Wordpress developer' to my resume. Tons of support from a great company.
    
*Cons*: Too many of plugins and themes. Administration screen gives me sensory overload, all I want to do is write. 
    
**[Jekyll](http://jekyllrb.com)**  
*Pros*: Seems like all the cool hackers (including gh-pages) are using Jekyll these days. Static page generator that uses markdown. Fully customizable. Completely self hosted.

*Cons*: If you struggle to install Ruby on your machine (like me) you are going to struggle using Jekyll. 

**[Calepin](http://calepin.co)**  
*Pros*: Static page generator. Minimal default template. Syncs markdown files from your [dropbox](http://db.tt/XZLyZkB). Allows for inline html.

*Cons*: You are stuck with the default template. No favicon support.

###Final Decision
I have chosen to go with Calepin, it satisfies literally every one of my requirements.
>By combining a service you already have with a syntax that’s easy to learn, Calepin is the easiest way to self-publish online.

It supports markdown, code highlighting, google analytics, disqus integration, clutter free, [dropbox](http://db.tt/XZLyZkB) syncing, just the right amount of customization, custom domains, rss feeds, tags, and categories out of the box, and takes only [seconds to setup](http://jokull.calepin.co/calepin-guide.html).
Although there doesn't seem to be a huge community, the developer has a [renewed mission to keep it alive](http://jokull.calepin.co/calepin-redux.html), which you can help fund at [gumroad](https://gumroad.com/l/DetH).

If you are looking for a static blog generator, enjoy markdown, but are not quite comfortable with gems and whatnot, then Calepin.co is for you.

###Reward Beer
[Lagunitas: Wilco Tango Foxtrot Ale](http://www.lagunitas.com/beers/index.html)

###Road Map

*    Use the RSS feed and IFTTT to auto tweet new posts
*    Research CNAME redirects of subdomains, if not buy a domain
*    Find out if it can handle large surges of traffic
*    See if there isn't a way to trick the site into having a favicon
*    Create a git repo of the posts for fun
*    Create a skeleton post for even faster project logging

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>