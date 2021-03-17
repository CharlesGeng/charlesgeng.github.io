---
title: "How to Setup My Personal Blog With Hugo, Github"
date: 2021-03-16T10:33:24+09:00
draft: false
tags: 
  - HUGO
categories: 
  - IT
---

## Install Hugo on your PC

Nothing special, just follow the instructions of official documentation [Here](https://gohugo.io/getting-started/installing/)

## Create a repository in github

- Create a repository with \<yourname\>.github.io

## Create the new site

- Use **hugo** command to generate the new site

```bash
hugo new site charlesgeng.github.io
```

- Checkout the repository from github

```bash
git init
git remote add origin https://github.com/CharlesGeng/charlesgeng.github.io.git
git fetch
git checkout origin/master -ft
```

- Add **mainroad** theme to the site.

```bash
git submodule add https://github.com/vimux/mainroad

```

- Setup **config.toml** file of the site
  - Enable Sidebar
  - Enable Main Menu
  - Enable Social Links

## Deploy the site

- commit and push the code to github
- Goto the **actions** of the repository, create a new workflow based on the documentation [here](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

**DONE!**
