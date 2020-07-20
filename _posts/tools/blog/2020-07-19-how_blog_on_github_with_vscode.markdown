---
layout: post
title:  "How to blog on github with VsCode"
date:   2020-07-19 17:13:41 +0800
categories: jekyll update
---
# How to blog on github with vscode

## Why I choose github page

I'm used to write noting in markdown and vscode+github can help me solve the image problem. Github page is free to me.

## What component it used

github page + jekyll + mask download + vscode

1. What is [Github Pages](https://docs.github.com/en/github/working-with-github-pages/about-github-pages)?

    > Github Pages are public web pages that are freely hosted on GitHub's `github.io` domain or a custom domain name of your choice.

2. What is [Jekyll](https://jekyllrb.com/docs/)?

    Jekyll is a static site generator. You give it text written in your favorite markup language(For me, it's markdown) and Jekyll can convert it to static website html to publish.

## Requirements

- git
- github
- [ruby](https://rubygems.org/pages/download)

## Set up environment

open a terminal

```bat
:: install jekyll
gem install jekyll

:: install bundler, bundler use gemfile to manage gem packages
gem install bundler

:: install Github-
gem install Github-Pages
```

Using window system installation pipeline as sample.
We have to parts.

1. Configure github page on github

2. Configure local web site on jekyll
Then you can use git to sync blog local repo with github remote repo.

### How to use Github Pages to generate your first page

1. Create a new repository, name it with  `{your_username}.github.io`
2. After we created new repository, click `Settings` on top-right, Find Github Pages, Choose a theme you like. Then Github Pages will generate your website and jump to a git commit page automatically.
3. Click commit changes on the page. Then you can visit your website at `{http(s):{your_username}.github.io}`

Util now, you have generate your own webpage on github.io, you can upload blog on it. Following ,we will use jelyll to convert our blog text to static html and sync our website.

### How to create your first local website by jekyll

```bat
:: Create a new jekyll project, named it with blog
jekyll new blog

:: Enter the project folder
cd blog

:: build and run jeky project
jekyll serve
```

visit localhost:4000 to check.

### How to sync website to github

```bat
:: init jekyll project
git init

:: commit local modification to remote
git add .
gti commit -m "init my blog website"
git remote add origin http://github.com/{your_github_username}/{your_reposity_name}.git
git push origin
```

visit `http://{your_github_username}.github.io` to check

## How to vscode to blog

We have set up the environment of our blog website on Github Pages via jekyll. If you are used to write markdown text by vscode, your will feel good to write blog on vscode too.

Use vscode as maskdown editor with git and jekyll tool.

### Extension

- Markdown all in one(Edit and preview markdown)
- ImagePaste(Generate image on editing doc folder from paste)
- Jekyll Run(Run jekyll)

1. Image Paste

![1]({{ site.url }}/assets/2020-07-20-07-54-27.png)
![2](/assets/2020-07-20-07-54-27.png)
![3](/assets/img/2020-07-20-07-54-27.png)
![4](/2020-07-20-07-54-27.png)
## More

### How to choose a theme your like

https://github.com/pages-themes/minimal

- Add the theme-gem to your Gemfile
- add the theme to your _config.yml
- Run: `bundle install`(just to make sure the bundler is able to use it)
- Run: `bundle exec jekyll serve`

For example,

http://jekyllcn.com/docs/structure/

As the pages said,
we need to add `gem "github-pages", group: :jekyll_plugins`  
add `theme: jekyll-theme-minimal` to _config.yml

### Jekyll project structure

Your dynamic content, so to speak. The naming convention of these files is important, and must follow the format: YEAR-MONTH-DAY-title.MARKUP

## QA

1. Can i change the url of my Github Pages Page

https://github.community/t/change-the-url-of-my-github-pages-page/10313

## Reference

1. [如何使用Jekyll+GitHub Pages搭建个人博客站点](https://mp.weixin.qq.com/s?src=11&timestamp=1595149151&ver=2469&signature=MJG8pyJdZWV6bT8CTfUrVV7tTuCgMbsHzJD4CkNTz0uj3KV-XLAnn16AL*fBfJSU5IpQZkJNNLqGFK1EeVXRrxHxcF8m5brYUNfJRDsaRzJOK8hTUxxTL7r3fOc8vEhH&new=1)
2. [如何在 GitHub 上写博客？](https://www.zhihu.com/question/20962496)
3. [Creating and Hosting a Personal Site on GitHub](http://jmcglone.com/guides/github-pages/)