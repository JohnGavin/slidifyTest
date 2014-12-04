---
title       : slidify 
subtitle    : first try
author      : me
job         : yes please
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---


```r
library(slidify)
library(slidifyLibraries)
```

## author

create a new directory mydeck and add the necessary scaffolding. 
If you have git installed, it will initialize it as a git repo, checkout its gh-pages branch, add and commit everything. 
Finally, it will open index.Rmd for you to edit.

```r
author("mydeck")
```

```
## Creating slide directory at mydeck...
## Copying files to mydeck...
## Finished creating slide directory...
## Switching to slide directory...
## Initializing Git Repo
## Checking out gh-pages branch...
## Adding .nojekyll to repo
## Opening slide deck...
```

---

## Slide 2

## Read-And-Delete
Edit the YAML front matter (if you don't know what it is, just replace everything to the right of the : in the lines between the --- right at the top). Edit the deck, making sure to separate your slides by a blank line followed by three dashes ---.

1. Edit YAML front matter
2. Write using R Markdown
3. Use an empty line followed by three dashes to separate slides!

--- .class #id 




