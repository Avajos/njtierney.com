---
title: 'Naming Things'
author: ''
date: '2018-06-20'
slug: naming-things
categories:
  - rstats
  - Teaching
tags: []
---

> There are only two hard things in Computer Science: cache invalidation and naming thing
> -- Phil Karlton  ([seen in r-packages](http://r-pkgs.had.co.nz/package.html))

I'm not really sure what cache invalidation is, but I certainly agree that naming things is pretty damn hard. I thought it would be
interesting to share some thoughts and discussion that I've been having about
naming packages. There was some [recent  discussion on tidy names](https://twitter.com/sctyner/status/1008794932444884996) on Twitter, and I
felt like this was a good time to discuss this idea. Well, that, and this blog post
has been sitting in draft form for 1 year on my computer.

# Naming Packages

This initial discussion began at the [rOpenSci Unconf in 2017](http://unconf17.ropensci.org/), where [Noam Ross](https://github.com/noamross) made the point that there are a few different ways to thing about naming packages in R, which he described fell into three styles, the oldschool, the modern, and the post modern. I thought it would be fun to discuss these.

## The oldschool (mixedCaseRs)

The oldSchool namer generally mixes case in an R package, often capitalising the 
"R", or going all in on ALL CAPS.

Examples:

- [twitteR](https://cran.r-project.org/web/packages/twitteR/)
- [formatR](https://cran.r-project.org/web/packages/formatR/)
- [UpSetR](https://cran.r-project.org/web/packages/UpSetR/)
- [ochRe](https://github.com/ropenscilabs/ochre)
- [MASS](https://github.com/ropenscilabs/MASS)
- [Matrix](https://cran.r-project.org/web/packages/Matrix/)

Although personally I wouldn't use this style as it can make it difficult to type, they have a certain charm, and are easy to google - provided you spell it right. And these are still seriously useful - Matrix provides extensive support for modelling, UpSetR produces great plots as an alternative to venn diagrams.

## The Modern (lowercasers)

The modern namer has everything in lowercase and usually carefully places an `r`. For example:

- [dplyr](https://github.com/tidyverse/dplyr)
- [tidyr](https://github.com/tidyverse/tidyr)
- [purrr](https://github.com/tidyverse/purrr)
- [furrr](https://github.com/DavisVaughan/furrr)
- [knitr](https://github.com/tidyverse/knitr)
- [naniar](https://github.com/njtierney/naniar)

These names are pretty popular amongst the `tidyverse` set of R packages

## The Post Modern (names)

This involves using just the original name, as is. This name must also be a thing, or a person.

Examples:

- [broom](https://github.com/tidyverse/broom)
- [checkers](https://cran.r-project.org/web/packages/twitteR/)
- [forecast](https://cran.r-project.org/web/packages/forecast/) 
- [greta](https://cran.r-project.org/web/packages/greta/)
- [fable](https://github.com/tidyverts/fable)
- [english](https://cran.r-project.org/web/packages/english)

Notably, `forecast` and `english` were postmodern before modern package names existed.

## The "gg"

The growth of `ggplot2` packages to add extra themes or geoms, starting with `gg`, these packages let you know what they're on about:

- [ggthemes](https://github.com/jrnold/ggthemes)
- [gglabeller](https://github.com/AliciaSchep/gglabeller)
- [ggforce](https://github.com/thomasp85/ggforce)
- [gganimate](https://github.com/thomasp85/gganimate)
- [ggalluvial](https://github.com/corybrunson/ggalluvial)
- [ggtree](https://github.com/GuangchuangYu/ggtree)
- [ggfocus](https://github.com/Freguglia/ggfocus)
- [gghighlight](https://github.com/yutannihilation/gghighlight)

The variety in all of these packages speaks to the utility, extensibility, and general awesomeness of `ggplot2`.

## Tidy-preface

With the announcement of The Tidyverse being made official by Hadley at UseR! in 2016 (see the [video](https://channel9.msdn.com/Events/useR-international-R-User-conference/useR2016/Towards-a-grammar-of-interactive-graphics) around 44 minutes) - there has been a trend of packages to preface their name with `tidy`:

- [tidytext](https://github.com/juliasilge/tidytext)
- [tidygenomics](https://github.com/const-ae/tidygenomics)
- [tidyzillow](https://github.com/ChandlerLutz/tidyZillow)
- [tidylex](https://github.com/CoEDL/tidylex)
- [tidycensus](https://github.com/ColoradoDemography/tidycensus)
- [tidyhydat](https://github.com/ropensci/tidyhydat)
- [tidykml](https://github.com/briatte/tidykml)

This is super cool, and a neat way to find useful packages. It's also worth mentioning that the tidyverse is only officially about 2 years old - and there has been a lot of really nice, positive [growth in R packages](https://github.com/tidyverse), [community](https://community.rstudio.com/), and [a team](https://github.com/orgs/tidyverse/people) of great people working on making great sofwtware.

## And more?

There are for sure other ways to categorize the names - I don't think that you can categorize the whole naming process of R packages into just three categories - there is a rich process that happens when you name something, and I won't want to distill it down to a few labels! 

# How to make a name?

Coming up with package name often takes a lot of time and thought. Personally, I've changed the names of the packages `visdat` and `narnia` three times. `visdat` was initially [`footprintr`](https://github.com/njtierney/visdat/commit/a350e50d210ab99939b53b22e2e2013e7e492f80), then `vizdat`, and then finally `visdat`. `narnia` was initiallly [`ggmissing`](https://github.com/njtierney/narnia/commit/a161b7c5707e0c5041467d8f7228c11afb5e2b29), then `naniar`, then `narnia`, then back to `naniar`. Why the changes from `narnia` and back and forth? Well, mainly I was worried about some awkward cease and desist letters from the estate of CS Lewis once the package got on CRAN, and I'm not really sure how to change the name back on CRAN - I'm pretty sure that once it is on CRAN, that's it.

But, my story aside, here are some general tips.

I find that I generally need to sit on a name for a while and use it, describe
it to a few people. I find that once I state the name of the package to them, they often have to ask how to spell it, and if that process feels difficult multiple times, and if I can't work out how to explain why I named it that, then I generally try and rename it. Often this comes down to a few things:

- Is the package name hard to say?
- Is the package name hard to spell?
- Can you remember the name of the package?
- Does the package name evoke the task it does, or perhaps fit into some sort 
  of larger pun or story.
  
# Further resources for naming
  
I would look at the [`available`](https://github.com/ropenscilabs/available) package for checking if the name exists. Maybe one day this will come up with something creative or unusual.

Hadley has a [good guide](http://r-pkgs.had.co.nz/package.html) to naming packages, but I think that this process requires a few iterations.

Also another post by [Yihui Xie](https://yihui.name/en/2017/12/typing-names/) has a good post on naming things - make sure it is easy to type!
