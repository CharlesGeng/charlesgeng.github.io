---
title: "How to Setup My Personal Blog With Hugo, Github"
date: 2021-03-16T10:33:24+09:00
draft: true
tags: 
  - IT
  - HUGO
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
