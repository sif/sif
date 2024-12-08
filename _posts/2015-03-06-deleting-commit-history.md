---
layout: post
title: "Deleting Commit History"
categories: github
tags: github git
---

Change your directory to where you cloned the repository.

1. `git checkout --orphan latest_branch`
2. `git add -A`
3. `git commit -am "commit message"`
4. `git branch -D main`
5. `git branch -m main`
6. `git push -f origin main`
7. `git gc --aggressive --prune=all`
