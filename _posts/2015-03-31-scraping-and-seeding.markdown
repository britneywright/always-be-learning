---
layout: post
title:  "Scraping and Seeding"
date:   2015-03-31
---

This weekend I took part in a hackathon of one. A few cities had baseball themed hackathons, but since they weren't in my area I decided to work on a project on my own. The result: [Can I get a Bobblehead Today?](canigetabobbleheadtoday.com). It's a pretty straightforward rails app. When a user visits the site they are told whether or not there any Major League Baseball teams are giving away bobbleheads on that particular day. If they are the site lists which games and what the bobblehead promotion is. I've been in a rut lately so it felt really good to start and finish a project. There's definitely room for improvement and more I could do with it, but I reminded myself to stay in the hackathon mindset and make something that I could finish and others could use as soon as possible.

##Scraping sites with asynchronously loading pages

The first thing I had to do for the app was scrape all of the MLB team giveaway schedules. I've scraped sites and files before using Nokogiri and Ruby's built in Open-Uri so I thought this would be a piece of cake. When I tried to scrape the site the content within the schedule div was empty though, but when I inspected schedule elements on the page I saw the content. I realized the schedule data was loaded in with javascript and thanks to a [stackoverflow post](http://stackoverflow.com/questions/11525599/how-do-i-scrape-data-from-a-page-that-loads-specific-data-after-the-main-page-lo) I learned that Open-URI retrieves the page before the javascript loads, so I needed an alternative to fully load the page. Enter [Watir-Webdriver](http://watirwebdriver.com/). It's built on Selenium and will fully load browser pages. I created a rake task to load the schedule pages, save the content and then scrape it with Nokogiri for the bobblehead giveaway dates.

##Seeding databases

For this project I wrote two simple acceptance tests. One that indicated what a user should see if they visit the site on a day where there are no bobblehead giveaways, and another or days when there are bobblehead giveaways. Based on the data I scraped I chose one date where I knew there would be bobblehead giveaways and a date where there wouldn't be. In the browser everything appeared as I intended, but when I ran my tests they failed. At first I thought I set up Timecop incorrectly, but then realized the rake task I wrote only added data to my development database. I checked this by typing "rails c test" and then checked Game.all to see if any games were in the database. Since I needed the exact same data in the producion database also I decided to make a rake task to add all of the games to a the database seeds file. Big thanks to Stefan Wintermeyer for providing this [blog post](http://www.xyzpub.com/en/ruby-on-rails/3.2/seed_rb.html) that served as a good guide.

##Creating font-faces

I wanted to use an athletic style font-face in the app and I'm a big fan of the [Promesh](https://www.behance.net/gallery/PROMESH-A-Free-Athletic-Font/7094057) one by Paul Reis. The only problem is the font is only available in True Type Format. Enter Font Squirrel's free [webfont generator](http://www.fontsquirrel.com/tools/webfont-generator). It generates the font in additional formats, including WOFF, EOT, and SVG.
