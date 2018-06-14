---
layout: post
title: Editing this Website
subtitle: A post on how to edit protocols and website layout
gh-repo: bmford11/lotterhoslabprotocols
gh-badge: [star, fork, follow]
tags: [test]
---

This website was created from the [daattali/beautiful-jekyll](https://github.com/daattali/beautiful-jekyll#readme) Github repository
Some basics:
The /lotterhoslabprotocols project was created under Brett's personal webpage bmford11.github.io, but now may reside under Katie's personal GitHub site.
View the Test markdown post to help you understand how to create pages

The steps to creating a project under a personal GitHub page were a bit confusing, but this is what I did:
1. Created my personal page following the [instructions](https://github.com/daattali/beautiful-jekyll#readme).
This includes forking original repository, and renaming repository under settings
2. Create a new repository for project with title of project (e.g., lotterhoslabprotocols)
3. Now you need to duplicate the beautiful-jekyll respository to this project repository, but GitHub won't let you fork it again
4. So I git cloned the bare repository to my local computer

`git clone --bare https://github.com/bmford11/bmford11.github.io.git`

5. I then cd into that directory
'cd bmford11.github.io.git'
6. I then git pushed a mirror of the new directory to the project directory I created

`git push --mirror https://github.com/bmford11/lotterhoslabprotocols.git`

**THIS IS IMPORTANT**:

7. You then have to create all pages from the gh-pages branch
8. I edited the \_config.yml file quite a bit, using the original file to see how to create links in the navigation bar
(Basically, under navbar-links in \_config.yml, hit tab and type title of link you want in bar with a colon
You can then add sublinks which you do by typing two tabs, a dash, a space, the title of the sublink,  a colon, then the markdown (without extension) for the page in quotes

**Make sure the markdown is in your repository and is named as specified in your config file**

9. Pages are created by creating new markdown files, adding them to your repository, and adding them to the config file

