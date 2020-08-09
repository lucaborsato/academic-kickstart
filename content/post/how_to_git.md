---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "How To: git"
subtitle: "A beginner use of git, not complete and not perfect."
summary: "A beginner use of git, not complete and not perfect."
authors: ["admin"]
tags: ["HowTo", "Linux", "git"]
categories: ["HowTo"]
date: 2020-08-09T14:56:00+02:00
lastmod: 2020-08-09T14:56:00+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

## Create a repository

First create repository in bitbucket/github/gitlab (or whatelse) and copy the proper url.  

## Set the global config

From the pc you have to set the username:  

Run  

```bash
git config --global user.email "you@example.com"  
git config --global user.name "Your Name"  
```

to set your account's default identity.

## Init and commit local directory

If you have already a non-empty folder locally:  

```bash
cd local_folder  
git init  
git add -A .  
git commit -m "My first commit"  
git remote add origin <url>  
git push -u origin master
```

## Add - Commit - Push

When everything is properly set-up:  

```bash
git add -A .  
git commit -m "My running commit"  
git push -u origin master
```

## Branching

```bash
git checkout -b MyBranch  
git push --set-upstream origin MyBranch
```

This is shorthand for:  

```bash
git branch MyBranch  
git checkout MyBranch  
git push --set-upstream origin MyBranch
```

then start coding and  

```bash
git add -A .  
git commit -m "My first MyBranch commit"  
git push -u origin MyBranch  
```
