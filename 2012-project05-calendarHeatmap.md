Title: Project 5: Calendar Heatmap in Google Docs
Abstract: Vizualizing my half marathon training schedule.
Date: 2012-05-02
Author: Cris Noble
Slug: calendarHeatmap
Tags: learn, data, data vizualization, google docs, excel, heatmap, calendar, quantified self
Category: speed project

*TLDR: I made [this](https://docs.google.com/spreadsheet/ccc?key=0AhKa_IsEMANEdG1nWmhLZ2tRbDNBMzhsNjZ5MmdzbUE#gid=2) because calendar heatmaps are aweome.*

###Backstory
If you have not seen a calendar heatmap yet, you are missing out. I saw one over at the [revolution analytics blog](http://blog.revolutionanalytics.com/2009/11/charting-time-series-as-calendar-heat-maps-in-r.html) and became obsessed. Not only is it a beautifuly minimal calendar, but it is so easy to spot changes in data over time. In an instant you can compare days, weeks, months or years.

###Creating a calendar heatmap in GoogleDocs.
Step 1: We need some data. I just finished running a half marathon, during the training I recorded my daily miles. Time encoded data that changes over time is perfect for this kind of visualization.  
Step 2: Set up the grid, I am sure there is an automatic way to do this but I did it manually.  
Step 3: Sum up the miles for each date (see below).  
Step 4: Use conditional formatting to color in the squares and the text.<!--add a screen shot here -->
Step 5: Your done!

###The Demo
<iframe width='500' height='410' frameborder='0' src='https://docs.google.com/spreadsheet/pub?key=0AhKa_IsEMANEdG1nWmhLZ2tRbDNBMzhsNjZ5MmdzbUE&#038;single=true&#038;gid=2&#038;output=html&#038;widget=true'></iframe>

###Go ahead, change the data.
By using GoogleDocs' built in forms we can automatically update the data. Fill out the form below and watch the chart above update.

<iframe src="https://docs.google.com/spreadsheet/embeddedform?formkey=dG1nWmhLZ2tRbDNBMzhsNjZ5MmdzbUE6MA" width="760" height="330" frameborder="0" marginheight="0" marginwidth="0"></iframe>

If you want to make one of your own, you can use this [file](https://docs.google.com/spreadsheet/ccc?key=0AhKa_IsEMANEdG1nWmhLZ2tRbDNBMzhsNjZ5MmdzbUE&pli=1#gid=2) as your starting point.

###Relevant Code
Basic formula in each cell to sum the miles for the given day.

	:::Visual Basic.NET
	=sumif(entries!$B:$B,date($E$1,1,1)+7*D4,entries!$C:$C)

Note that this relies on the week number column and the number of days since January 1st to determine the current date to sum.

###Reward Beer
[Destihl Brew Works: DeadHead Double Red Ale](http://www.destihl.com/)

###Road Map

*    Import the GoogleDocs data with [Tabletop.js](http://builtbybalance.com/Tabletop/) for javascript manipulation.
*    Use my favorite library, [D3.js](http://mbostock.github.com/d3/talk/20111018/calendar.html), to make this look nicer.

***
MKSHT is the project log of Cris Noble. Follow him on [twitter](https://twitter.com/#!/Crisnoble "Cris Noble on Twitter"), [github](https://github.com/crismanNoble "Cris Noble on Github"), [Google+](https://plus.google.com/110702599026497087079?rel=author) or [forrst](http://forrst.com/people/crisman/posts "Cris Noble on Forrst"). You should check out his [homepage](http://crisnoble.com "Cris Noble's Homepage") and if you are feeling freindly, you could do it the old fashion way and send him an [email](http://crisnoble.com/sayhi).
***
<a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a>