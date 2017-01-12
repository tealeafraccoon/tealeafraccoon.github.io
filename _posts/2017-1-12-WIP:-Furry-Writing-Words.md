---
layout: post
title: Work in Progress - Word Frequencies in Furry Writing
---
A very quick post here with a work in progress. Below is a word cloud of the text of around 2000 stories I scraped from [SoFurry](http://www.sofurry.com/) a while back. As is typical with these things, I've stripped out the 500 most common English words, but beyond that it's basically just a word frequency summary (i.e., larger font size indicates the word appears more often).

I should stress I haven't really done anything sophisticated here, and this should be thought of as just a bit of fun rather than 'statistics' in any real sense. In particular, the data source is just the story content (via SoFurry's API) which I ran through an HTML converter I whipped up in [R](https://en.wikipedia.org/wiki/R_(programming_language)). This means that I haven't filtered out things like author preambles, so there's probably a bit of interference there. The dataset comes in at about 13 million words, with over 23,000 'cocks', 13,000 'dragons', and nearly 14,000 'insides'.

![alt text][cumpainnoise]

[cumpainnoise]: http://gdurl.com/Z4NL "cum pain noise"

Word cloud courtesy of [this](https://github.com/amueller/word_cloud) rather funky Python generator!

I have a few ideas for where to go with these data - right now I'm working on comparing the relative frequency of words in furry writing to English in general, which is throwing up some quite entertaining results; watch this space for that. I'm also interested in doing some more 'statsy' comparisons of SFW and NSFW content SoFurry's API is currently being renovated, so I can't do too much more for the time being, but figured I'd put this out while it's fresh in my mind!
