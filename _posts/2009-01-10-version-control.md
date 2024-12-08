---
layout: post
title: "Version Control"
categories: software_engineering
tags: software_engineering
---

* TOC
{:toc}

http://whatthecommit.com

"Google, Facebook, Microsoft, Uber, Airbnb, and Twitter all employ very large monorepos with varying strategies to scale build systems and version control software with a large volume of code and daily changes."



## Git

A tool for Source Code Management (SCM)



### Safe Updates

To keep track of the current version which is probably the safe one:

```
git rev-parse --short HEAD
```

Write down the resulting output from the above somewhere, then run:

```
git pull
```

If the next version is safe, then just enjoy.

But if it's unsafe, go back to the previous version:

```
git checkout (the resulting output from step 1)
```



### Gitea



```
git bundle create <filename>.bundle --all

git clone <filename>.bundle <folder>
```

If after pushing, `git status` doesn't show "nothing to commit", try `git add .`.



### GitHub

https://github.com/awslabs/git-secrets

- Open your fork at GitHub.
- "New Pull Request" -> "Switching the base" -> "Create a pull request"
- Scroll down and "Merge pull request".

Alternatively, to rebase to master [shortened](https://github.com/edx/edx-platform/wiki/How-to-Rebase-a-Pull-Request):

- git remote add upstream https://github.com/sif/source.git
- git fetch upstream
- git checkout master
- git rebase upstream/master

Check GitHub Desktop to see the changes. Alternative method not really helpful though.

```
git log --oneline --graph --decorate
```

To ignore .DS_Store:

```
git config --global core.excludesfile ~/.gitignore
echo .DS_Store >> ~/.gitignore
```

Delete prior revisions from a GitHub wiki so that only the most-recent # version of the content is available.

Clone the wiki:

```
git clone https://github.com/[user]/[repo].wiki.git
```

Remove the .git folder:

```
rm -rf .git
```

Reconstruct the local repo with only latest content:

```
git init
git add .
git commit -m "Initial commit"
```

Push to GitHub:

```
git remote add origin <github-uri>
git push -u --force origin master
```



### GitLab



## Netlify


