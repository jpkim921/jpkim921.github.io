---
layout: post
title:      "Rails Project"
date:       2018-09-24 19:52:38 -0400
permalink:  rails_project
---


My rails project is an app that someone interested in starting a Daycare might be able to use. At least to start out.

It’s a small app that right now can be used to keep track to registered parents and children. And parents to sign in to view their children and classrooms they child is in. The child was automatically be placed in a classroom depending on their age.

After having done the Sinatra and now this Rails project, I’m slowly realizing that it’s mostly true when others say when someone is working on a program, you’re actually programming a small percentage and the rest of the time you’re planning and reasoning out how the program/app is going to work and reading through documentation. Other than that, the design of the app is a whole other beast.

My own frustrations were that I had a hard time remembering the form helper arguments. Most of the time I looked over the Learn.co notes because that’s “how I learned it” and then tried to go through the documentations. For some, the documentations were easy to read and follow along but others felt like secret code I had to first decipher in order to use them.

One example of looking up documentation in my app was the date_select form helper.

```
date_select(object_name, method, options = {}, html_options = {})
```
For my use, I needed a parent to input a child’s brithdate in order to place him or her to an age appropriate classroom.

```
<%= f.date_select :dob, start_year: Time.now.year - 12, end_year: Time.now.year, order: [:month, :day, :year] %>

:dob is the model attribute

:start_year & :end_year are options to set up the earliest and latest years in the drop down. The default value is plus or minus 5 years but I choose 12 since  I decided the oldest age a child can be is 12.

:order is how you want the date fields to show up
Just have to keep in mind that the attribute will be split up into three different params.
```

"dob(2i)"=>"9", "dob(3i)"=>"24", "dob(1i)"=>"2018"

But don’t worry you can still use the attribute like normal.
