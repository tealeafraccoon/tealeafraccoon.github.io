---
layout: post
title: Foxes - statistically significant subs?
---

[Content warning: the following features discussion of furry pornography and cold, hard, p-values.]

The furry fandom is full of stereotypes, but in my experience the most pervasive (and long-lasting) concerns the sexual proclivities of foxes. The claim that 'all foxes are sluts' is so ubiquitous, in fact, that I was surprised I couldn't easily find someone who'd verified it with data. Luckily, I'm a statistician, a furry, and (clearly) have too much spare time, so I had a look myself.

I imagine most of those who read this are primarily interested in the conclusion, so I'll get that out of the way first. (For those interested in the methodology, and the various assumptions I decided to make, I go into a *lot* more detail below.)

So, the headline: in a sample of 207 images from the furry image board [e621.net](https://e621.net/) from the last 12 months, featuring a fox character with a penis engaging in penetrative sex with a character of another species (who also has a penis), the fox was the receiving partner in 141, or 68%. In other words, a fox is over twice as likely to bottom, rather than top. (In any reasonable formal test you could consider, this is a statistically significant finding, with a 95% confidence interval for how often foxes bottom of 61%-74%.)

### So, how did I get here?

While this may seem a simplistic (and certainly unsurprising) result, there is considerably more nuance to this problem than meets the eye. By far the most difficult - and under-appreciated - element of any statistical analysis is working out precisely what question you're trying to answer, and then finding the data to answer it. Here, my starting point was the crudely-phrased stereotype that all foxes are sluts, and my first job was working out how to turn this into a question I could gather data to answer in an objective a manner as possible.

A key aspect of this process is to form a dataset that is as unambiguous as possible. There is clear potential here for a lot of subjectivity, and to ensure fair results this subjectivity has to be minimized. Fairly quickly, I decided that the question would have to be restricted to whether foxes were more likely to top or bottom in a sexual context involving two partners. I'll acknowledge up front that this is quite a simplification, but it allowed me to form a dataset based around relatively simple rules.

#### It's all about sex (and penises)

The restriction to pictures involving two characters having sex excluded two fairly common types of image: oral intercourse and multi-character scenes. With the former, one can certainly argue that fellating a penis is a submissive act, but by no means exclusively (I saw numerous instances of tops fellating the bottoms mid-sexytimes, for example). To my mind penetrative sex is, in contrast, almost entirely unambiguous. The primary exception to this are dominant bottoms. These, however, are almost impossible to eliminate objectively, and so the question is restricted to topping and bottoming, rather than (e.g.) dominance and submission.

The exclusion of images with more than two characters removes some cases which are arguably unambiguous (such as a character being on the receiving end of the, er, 'attentions' of multiple others). However, in return it avoids complex issues such as a character who is both topping and being topped, or deciding how to classify a 'third wheel' who isn't directly engaged with the other characters.

A further consideration was the gender of participants. More precisely, my analysis - like much of the fandom - was largely concerned with penises. To be included in the dataset, both characters in the image must have the (apparent) potential to be the top, and so in particular no apparently heterosexual images were included. This may seem quite a big restriction, but I took the view that in such cases, genitalia rather than species played the bigger role in determining who was on top. By limiting myself to a penis-penis situation I avoid the risk of confusing the question of interest with the somewhat separate issue of whether fox characters are more or less likely to have a penis.

#### Characteristics

Moving beyond the sexual criteria, there were also decisions to be made about the characters involved. An early decision was to limit the dataset to original characters, rather than those from fiction. The question is fundamentally about fox furries themselves, rather than what furries (or furry artists) would like to see being done to Miles Prower. On the plus side, I've now become very adept at recognizing Fox McCloud from a small thumbnail (spoilers: he's usually the dude getting banged by Wolf O'Donnell).

Hybrids are a further complication (as always, amirite???). The question of interest, however, explicitly concerns foxes, and so fox hybrids (such as folfs) were excluded. Pure foxes having sex with non-fox hybrids, however, were considered fair game. Varieties of fox, such as fennecs and arctic foxes, were classified as foxes for the purposes of this study. This might outrage some, but the stereotype is seldom presented in the context a specific fox species (such as Vulpes vulpes), and besides, distinguishing between fennecs, arctic foxes, and other species, introduces a degree of subjectivity that I preferred to avoid. On a related note, fox-on-fox action was also discarded. If included, these would add one to both totals - foxes topping and non-foxes topping - having limited impact (although still a small amount) on the overall conclusion. Excluding these made life slightly easier, and also means the question can be framed explicitly in terms of foxes having sex with non-foxes.

#### Repeat customers

A surprisingly complex decision concerned individual characters. As we all know, some furries appear in more art than others, and so any attempt to form a sample of observations of foxes having sex would almost certainly result in some characters appearing multiple times. This raises the question of whether to allow multiple appearances by the same character.

The most obvious complication is that results could be influenced by just one or two individuals who happen to get a lot of art. As an extreme example, if 50% of my dataset contained the same fox who happened to be super into putting their penis into other furries' bottoms, that single fox would dictate the entire conclusion. This brings me back to basics: what question are we trying to answer? If you allow the same character to appear multiple times in the dataset, the question becomes 'if you pick a random piece of furry art featuring a fox having sex, what's the probability the fox is on top?'. However, I think the issue of a fox stereotype means the question should be 'if you pick a random fox furry, and they appear in a piece of furry art, what is the probability they're on top?'. This might seem like a subtle distinction, but it comes down to whether we want to ask if *furry art in general* tends to show foxes topping, or whether *the foxes themselves* are the ones into topping.

A related issue is fox characters who sometimes top, and sometimes bottom - how should they be counted? If we had access to all of a character's art, we might be able to say 'oh, this fox tops 80% of the time, and bottoms 20% of the time', and we might include them by adding 0.8 to the 'foxes top' count, and 0.2 to the 'foxes bottom' count. Of course, I don't have access to all the furry art in the world (thank goodness), and so instead I decided to only include the first image I encountered of any given character. This means that any foxes who exclusively top (or bottom) would necessarily count once towards their respective totals, while a switch would count once towards either total with probability approximately equal to how often they top or bottom. (If that last point seems confusing, consider our fox who tops 80% of the time: assuming that picking the first image I see is equivalent to picking at random from their collection of art, then there's an 80% chance I pick an image with them on top. Statistically, this *just about* works out to the same as if I added 0.8 to 'foxes top' and 0.2 to 'foxes bottom', once I've got a large enough dataset.)

#### Sauce plz

Having established precisely what types of image would form my dataset, the next decision was where to source them. The fandom has a variety of art sites, each with different properties. I didn't have a particularly strong reason for going with e621.net over the alternatives, but I didn't have a particularly strong reason not to, either. It's possible that similar samples of other art sites may yield different results, and I plan to look into that in future.

### Digging the data

Phew! So after all that thinking, I finally had a set of rules for forming my dataset. The last thing I needed to work out was my sample size. For this I could have used some statistical theory to calculate what size of sample I should aim for, but instead I just decided to sample the last 12 months of uploads to e621. (This easily covered even the more pessimistic sample size calculations I tried.) My selection criteria were therefore as follows:

- Images uploaded to e621.net in the previous 12 months.
- Image must contain precisely two original furry characters, where one character is unambiguously a fox and the other character is unambiguously not a fox, as defined above.
- Both characters are engaging in penetrative sexual intercourse.
- Both characters have a penis.
- Only the first instance (chronologically, based on upload time) of art featuring a given character is included.

The e621 search function allowed me to narrow down the previous year of uploads fairly efficiently, and I 'analyzed' every image that made it past this initial search to verify eligibility (a lot of fox on fox action made it through the filters). The dataset was then re-analyzed by an expert assistant with extensive experience of furry pornography (seriously, dude needs to get a job), helping verify the results and allowing us to discuss any disagreements. After all of this the final dataset consisted of 207 images, of which 66 featured a fox on top. A test of the null hypothesis that foxes top 50% of the time in such images results in a p-value of less than 0.000001 - in other words, the probability of observing results at least as extreme as this, if foxes were equally likely to top and bottom, is very *very* small. (For the stats nerds: the p-value was below this threshold for a 1- or 2-sided test. I generally don't really like 1-sided tests out of principle, and reported the 2-sided interval above in the summary. In case you're wondering - and it admittedly seems reasonable here - the 95% 1-sided confidence interval for foxes bottoming works out to 62%-100%.)

### Limitations

As with any analysis, there are numerous limitations and caveats. I've tried to address as many as possible above in describing my approach, but there are a few additional ones that bear explicit mention. (I don't doubt others may spot additional flaws, in which case please pass them on!)

The biggest limitation is that this is necessarily restricted to analysis of visual art. As such, the results must be framed in terms of 'foxes who have at least one visual art commission' rather than 'all fox characters'. For example, it may be that submissive foxes are more likely to commission art than dominant ones, which would drastically bias the sample. A related issue is limiting the sample to one website, and only one year's worth of uploads. Again, perhaps those who upload content to e621 prefer art with foxes on the receiving end, or this is a pattern that has only existed for the last year. These issues can be addressed by widening the sample to other sites and longer timeframes, but this is quite time consuming (and my instinct is that the results wouldn't change).

### Where next?

If you've read all the way down here, this has probably seemed like quite a lot of work for a pretty simple (and unsurprising) conclusion. Still, even the most obvious truths should be backed up by evidence, and I hope I've managed to do that. I also hope that I've demonstrated how statistics isn't just about knowing a few complicated equations to turn a dataset into a conclusion (indeed, the actual statistical analysis here was trivial). Statistics is much more about the careful thought that's required to properly define a question of interest, and determine what data to use (and how to collect them) to answer it.

One of the next ideas I want to pursue is an offshoot of this result, looking at which species tend to be the most (or least) dominant. There were some early signs in this dataset, for example, with horses never on the receiving end of a fox penis, but being on top 14 times. It certainly seems likely that horses (and other well-endowed species) would be more likely to top, and I have a related set of results which I hope to write up soon that ties into this idea.

For now though, we can finally rest assured that the fox stereotype (at least in the manner I've defined it here) is a statistical reality, and I managed to write it up without making any dick jokes. Knot even one.
