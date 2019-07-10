---
title: 'Just Quickly: How to show verbatim inline R code'
author: ''
date: '2019-07-10'
slug: jq-verbatim-inline-r
categories:
  - rstats
  - rmarkdown
  - teaching
tags: []
---

I've recently asked on the [Rstudio community page how to make code chunks appear verbatim](https://community.rstudio.com/t/question-feature-request-code-chunk-option-verbatim-true/33521). 

Not sure what I mean by this? Well, it comes up when you are teaching people about rmarkdown. One of the issues is that you want to show people what an rmarkdown code chunk looks like - not just echo the output. 

For example, here is an rmarkdown code chunk:


```r
library(ggplot2)
ggplot(airquality,
       aes(x = Ozone,
           y = Solar.R)) + 
  geom_point()
```

<img src="/post/2019-07-10-jq-verbatim-inline-r_files/figure-html/chunk-example-1.png" width="672" />

But - you can't see that I have set two chunk options so that no warning message is given - `warning = FALSE, message = FALSE`.

You could instead demo everything on your computer, or show a screenshot, but that just isn't practical, or scalable, and kind of goes against the grain of rmarkdown and these ideas of [literate programming].

There are some solutions to this in the community link above, which link [Yihui's blog post on this](https://yihui.name/en/2017/11/knitr-verbatim-code-chunk/). For code chunks, Yihui demonstrates how I can show these code chunks - what I want to show is this:

````
```{r chunk-example, warning = FALSE, message = FALSE}
library(ggplot2)
ggplot(airquality,
       aes(x = Ozone,
           y = Solar.R)) + 
  geom_point()
```
````

Which, you can generate with code that looks like...well, I can't actually seem to generate the code to show _how you write that_ - I just get this:

`````
````
```{r chunk-example, warning = FALSE, message = FALSE}
library(ggplot2)
ggplot(airquality,
       aes(x = Ozone,
           y = Solar.R)) + 
  geom_point()
```
````
`````

But you can look into [Yihui's blog post](https://yihui.name/en/2017/11/knitr-verbatim-code-chunk/) for the details, or at the markdown source for my post [here]()

# So, how to do the same thing for inline code?

In any case, I came here to show _yet another amazing feature of knitr_ that I did not know about until this morning. Just like you want to show the verbatim code code chunk, you can do the same thing with _inline code_.

Say I want to list the names of the month in text, say something like this:

> The months of the year are January, February, March, April, May, June, July, August, September, October, November, December

You can show people the inline R code bit using the function `knitr::inline_expr("month.name")` in you inline expression:

> The months of the year are `` `r month.name` ``

And if you want to see how I wrote that, I think the easiest way is to see what the markdown code here.

# End

That's it - use `knitr::inline_expr("text")` to show a verbatim inline expression in your code.
