+++ 
date = 2025-06-15T18:32:08+08:00
title = "How to start a blog on GitHub Pages with Hugo"
description = "A guide to creating and deploying a personal blog using Hugo and GitHub Pages"
author = "Anton(Shuqiao) Li"
tags = ["hugo", "blog"]
categories = ["tech"]
+++

GitHub Pages offers a free and robust platform for hosting personal blogs.
There are several static site generators available for this purpose.
Hugo is particularly well-suited for technical blogs due to its performance,
flexibility, and extensive theme library. This guide will be demonstrated mainly
on Windows and is intended for beginners with basic familiarity with Git and command-line operations.

## Steps

### Create a GitHub Pages repo

![create-gh-repo](/images/create-gh-repo.png)

The repo name **must be** `<username>.github.io`, for example, 
my username is `celestialli`, so my repo name should be `celestialli.github.io`.

Check "Add a README file" so that the repo will set main as the default branch.

### Install Hugo

First of all: Install Git.

Go to [Hugo GitHub release page](https://github.com/gohugoio/hugo/releases),
choose your platform and download the extended_withdeploy version. 
For example, I'm planning to use hugo on Windows and I have x64 CPU.
I'll download `hugo_extended_withdeploy_0.147.8_windows-amd64.zip`.

After extracting the zip file, add the .exe path to the system `Path` environment variable,
so that we can call hugo in a terminal anywhere.

To verify your installation, run `hugo version` in your terminal

### Create local Hugo project

Open a git bash on a desired path, run `hugo new site <username>.github.io`.
This will create a new directory named `<username>.github.io`.

### Configure Hugo project

We will use hugo-coder theme as an example.

```bash
cd <username>.github.io
git init
git submodule add https://github.com/luizdepra/hugo-coder.git themes/hugo-coder
```

Open hugo.toml, add or change `theme = "hugo-coder"`.

```bash
hugo server
```

Then you visit the output address, you'll see your blog locally.

### Host on GitHub Pages

Link your local directory to your github repo `<username>.github.io`. To do so, you'll
most possibly run:

```bash
git remote add origin <remote-url>
```

![gh-url](/images/gh-url.png)

The `<remote-url>` can be https or ssh url. It's up to you.

Then you follow the [Hugo official guide](https://gohugo.io/host-and-deploy/host-on-github-pages/)
to configure the workflow.

Then you can visit your page with `<username>.github.io`. Everytime you push to the main branch of the repo,
a workflow will start and deploy the update to the site.

### Add a post

To add a post, you can see [Hugo official guide](https://gohugo.io/getting-started/quick-start/#add-content).

After adding a post, you just commit and push the update from local machine to the repo. The update will deploy
automatically.

## More Information

### Use other themes

Go to [Hugo themes](https://themes.gohugo.io/). Choose one you like, and click "Download". It will teach you how
to install.

### Configure your site

You may configure your site with hugo.toml. To see how to configure the site, you may see an example at 
`themes\<your themme>\exampleSite\hugo.toml`
