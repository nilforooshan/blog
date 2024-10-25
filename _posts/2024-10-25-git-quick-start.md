---
layout: post
title: "git quick start"
date: 2024-10-25
Categories: git
permalink: /:title
---

Create a new repository on the command line.

```sh
echo "# repository" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/<USER>/<REPONAME>.git
git push -u origin main
```

or push an existing repository from the command line.

```sh
git remote add origin https://github.com/<USER>/<REPONAME>.git
git branch -M main
git push -u origin main
```

