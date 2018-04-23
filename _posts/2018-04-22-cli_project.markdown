---
layout: post
title:      "CLI Project"
date:       2018-04-23 03:21:27 +0000
permalink:  cli_project
---


The gem is called Surly-Bikes. It hasn’t been published because I’m not sure if I'm allowed to. Just using their site for my project.

This gem scrapes all the bikes based on the category that it’s in. It will then produce a list of bikes where users are able to choose the one they want to look at.  After the bike is chosen, the gem will output information about the bike and all its specifications such as what parts it’s built up with.

From this project I learned how IMPORTANT planning in the beginning is. That seems like common-sense, but the first design idea that I thought was ok turned out to be annoying.  I ended up spending a lot of time looking for other ways to do certain things. I also found testing and waiting for the data to load to be very frustrating and annoying as well.

The way it worked out, every single bike’s webpage was made so that the Info, Specs, Geometry, and Frame Highlights all had their own links to scrape. So essentially, I had to scrape 4 links for each bike. Doing that for close to 30 bikes took forever. I’m not totally sure if it was the way I coded, the internet connection, slow computer, or any other factor, but doing it similar to the Student Scraper lab didn’t work for me. In the student lab, all the scraping and objects were created before anything else began.  Therefore I ended up starting my project all over again.  It was a good learning experience.  I took a lot of notes while I was doing it the first time so it was more of picking and selecting which block I wanted to use or edit.

The second time, I broke down the steps and scraped it in sequence.  So it’ll scrape the bike categories first, then once one is picked, it’ll bring up the list of bikes. Then, it’ll scrape the bike’s info, geometry, etc. of the bike chosen and output the info. It still took a tiny bit of time, but it was much much better than the way it was running the first time.

It seems so simple now in hindsight, but I also know this wasn’t the only issue I ran into.  I also had issues with planning at the start of the project.  My advice is that once you find a website to work on, scrape the heck out of it to help you plan your project. Get comfortable setting projects up like requiring files, requiring gems, the environment file and the gemfile when creating a gem. Also get comfortable using PRY. You don’t have to be a master at it but be familiar with it.

I want to leave you guys with a method that I feel saved my sanity. No matter how hard I tried, I couldn't find a way to make a hash directly from the Nokogiri data so I tried to do it another way.  I ended up using #zip to take two arrays and created a nested array so that I could transform it into a hash with #to_h. 

```
a = [ 4, 5, 6 ]
b = [ 7, 8, 9 ]

a.zip(b) => [[4, 7], [5, 8], [6, 9]]
a.zip(b).to_h => {4=>7, 5=>8, 6=>9}
```

FYI: Shouldn't really be an issue but if you have Ruby version < 2.0, #to_h doesn't exist. I ran into that problem and just about blew up a part of my brain.

