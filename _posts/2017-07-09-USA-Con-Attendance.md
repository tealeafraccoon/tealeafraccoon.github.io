---
layout: post
title: USA Furry Convention Attendance - An Exploratory Analysis
---
After an exciting trip to Anthrocon, what better cure for PCD than playing with furry convention attendance data? I grabbed the numbers from [this](http://en.wikifur.com/wiki/Timeline_of_conventions_by_attendance) wikifur page, which claims to list every 'convention' with at least 100 attendees. This immediately presents some problems, which given how informal this is I'm definitely not going to try and deal with, but will at least mention in the interests of transparency:

- It's a wiki, so there will be a lot of error and missing data. (There are various statistical ways of handling these issues, but nobody's got time for that on a Sunday.)
- 'Convention' means different things to different people. For example, the UK LondonFurs meets regularly surpass the 100 attendee figure, but aren't listed (nor are their summer and winter events), whereas various FurBowls and other one-day events are included. This kinda falls under the 'it's a wiki' issue.
- By only listing events with over 100 attendees we get a slight self-selection problem, but we can sidestep this by defining 'convention' to mean 'an event with over 100 attendees' (or even, 'an event with over 100 attendees listed on that particular wikifur page'). Moreover, given the total numbers I'm dealing with (and how informal the analysis), events with fewer than 100 people aren't really going to affect what I'm going to do too much.
- I'm going to limit focus to events listed as taking place in the USA, primarily because I don't think it's reasonable to assume American event demographics will be similar to those from the rest of the world. Moreover, data from other countries (even Canada) seem *much* more patchy, and only make up 15% of con attendance over the time period, so this doesn't cost a huge amount.

With all that said, and a reminder that none of what follows is presented with any particularly strong conviction, let's take a quick journey through the data. First up, it's everyone's favourite statistical pal: a plot of the numbers!

![alt text][figure1]

[figure1]: http://gdurl.com/CAxu "Rawr data"

First impressions count, and with this beauty we can see a couple of possibilities. One is that the growth rate looks like it could be some kind of exponential function (i.e., growing faster and faster over time), the other is we could be looking at two (or more) straight-line patterns that are joining together (more on this in a minute).

##### Transform and roll out

We can investigate the former through something known as a [power transform](https://en.wikipedia.org/wiki/Power_transform). This is a bit mathy (so don't worry about it too much if it looks boring/scary), but the basic idea is to try and change the y-axis numbers (the attendance figures) in such a way as to make the relationship between year and attendance look like a straight line. A common approach is to take the square root, or a logarithm, but the fundamental principle is to apply the same transformation to every point. Once we find the best way to transform the data (I actually used a [Box-Cox transformation](https://en.wikipedia.org/wiki/Power_transform#Box.E2.80.93Cox_transformation), stats-fans), we can 'un-transform' to get a curve on the original scale. I'm personally always a bit mistrustful of this approach, but it does serve a purpose, and if we run the numbers we get the following:

![alt text][figure2]

[figure2]: http://gdurl.com/8Als "Curve time"

The right-hand plot shows the 'straight-line' relationship the analysis has determined (if you look at the y-axis you'll see it's not scaled in the same way), while the left-hand plot shows the original data with a curve corresponding to the equation that has been fit. I'm not super happy with this model - there's a slight pattern in the right-hand plot that would concern me if this was a more serious analysis - but it'll do for now. For the equation fans out there, the final model is 'Attendance⁰⋅²²² = -562.8 + 0.2845×Year', and would estimate 2017 total con attendance at about 48,815. We'll see how that goes at the end of the year!

##### If you don't like curves...

An alternative approach is something called a [piecewise linear model](https://en.wikipedia.org/wiki/Piecewise_linear_function). Rather than supposing the relationship between year and attendance is a curve like the one above, we might instead suppose that there are straight-line (i.e., linear) relationships between year and attendance that change at certain times. For example, if we look at these data, there seems to be slow growth from 1990-2005 or so, then much steeper growth after that. A change in slope can reflect an important underlying change in the population (such as a certain generation turning 18, for example).

Of course, we want a more objective way of establishing these relationships than just looking at the graph, so for that we can carry out an analysis that tries to automatically find where these changes in slope occur. A reminder that as statisticians we're always trying to explain the patterns we see in the data, so here we want to find the set of straight lines that best fit the points on our graph. We could accomplish this by drawing a straight line between every point, but that isn't very interesting (and won't help us identify any underlying patterns). Instead, we try and find the simplest model (i.e., the model with the fewest changes in slope) that still explains enough of what we're seeing to be useful. If we try this out with these data, the recommended model actually has *two* changes in slope: one in 2005 and another in 2012 (although the change in 2012 isn't particularly large). We can then plot this model on the data as follows:

![alt text][figure3]

[figure3]: http://gdurl.com/Xc8V "Line fun"

This approach does a reasonable job in fitting the relationship in the later years, but 1990-2005 looks like a poor approximation to me, so make of that what you will. (In case it's of interest, this model predicts 2017 con attendance of about 50,810, pretty similar to the prediction of the exponential model.)

###### *Con*clusions

Overall, I'm more convinced by the power transform fit than the piecewise linear one; it seems to visually fit the data well (and does a little better if we test the two model fits more formally) and I reckon an exponential relationship makes more intuitive sense for population growth. What does seem unambiguous is some sort of change beginning in 2005, which not only shows up very strongly in the original data, but is also reinforced by the piecewise linear model (I'm not so convinced by the proposed 2012 changepoint, but I suppose time will tell on that front).

With such limited data we can't hope to do more than speculate as to why, but I do wonder if we're seeing a 'millennial effect' start to take hold around the 2005 mark. [Most studies](https://en.wikipedia.org/wiki/Millennials#Date_and_age_range_defining) seem to put this generation beginning in the early 1980s, and so perhaps we're seeing this group start to find themselves with the independence and disposable income to start attending (or maybe even running) cons in earnest from around the early 2000s. There are countless other possible explanations, however, and I'd love to hear yours - you can contact me by email (see 'About', above) or on Twitter [@tealeafraccoon](https://twitter.com/tealeafraccoon/)!
