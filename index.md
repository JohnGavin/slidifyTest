---
title       : 
subtitle    : 
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---



### http://applyr.blogspot.co.uk/2014/05/rstudio-pushing-to-github-with-ssh.html
If RStudio prompts you for a username and password every time you try to push your project to Github, open the shell (Git menu: More/Shel...) and do the following:


git config --global user.name "john.b.gavin@gmail.com"
git config --global user.email "john.b.gavin@gmail.com"
ssh-keygen -t rsa -C "john.b.gavin@gmail.com" 

Your identification has been saved in /home/rstudio/.ssh/id_rsa.
Your public key has been saved in /home/rstudio/.ssh/id_rsa.pub.
The key fingerprint is:

In RStudio, go to menu Tools / Global options / Git SVN / View public key and copy the key to your Github account setting (Edit profile / SSH keys / Add SSH key).

To check that ssh-authentication works, try to run
ssh -T git@github.com

git config remote.origin.url git@github.com:JohnGavin/slidifyTest.git



## Slidify

This step generates a html slide deck from index.Rmd. It is a static file, which means that you can open it in your browser locally and it should display fine.


```r
slidify("index.Rmd")
```

```
## 
## 
## processing file: index.Rmd
```

```
##   |                                                                         |                                                                 |   0%  |                                                                         |......................                                           |  33%
##   ordinary text without R code
## 
##   |                                                                         |...........................................                      |  67%
## label: unnamed-chunk-2
##   |                                                                         |.................................................................| 100%
##   ordinary text without R code
```

```
## output file: index.md
```
---

## Publish
Publish your deck to github. 
Login with your github account and create a new repository. 
Note that Github will prompt you to add a README file, but just use the defaults so that your repo is empty. 
You will need to have git installed on your computer and be able to push to github using SSH

# replace USER and REPO with your username and reponame
publish(user = "JohnGavin", repo = "slidifyTest")
publish(user = "github.com", repo = "johngavin/slidifyTest", host = 'github')

getOption('github.user')
  system('git add .')
  system('git commit -a -m "publishing deck"')
  system(sprintf('git push git@github.com:%s/%s gh-pages', username, repo))
  link = sprintf('http://%s.github.com/%s', username, repo)
  message('You can now view your slide deck at ', link)
  browseURL(link)
  
git@github.com:JohnGavin/slidifyTest.git
https://github.com/JohnGavin/slidifyTest.git
https://gmail.com.github.com/slidifyTest https://github.com/JohnGavin/slidifyTest

https://johngavin.github.com/slidifyTest https://github.com/JohnGavin/slidifyTest

## Read-And-Delete

1. Edit YAML front matter
2. Write using R Markdown
3. Use an empty line followed by three dashes to separate slides!


--- .class #id 

