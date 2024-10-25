---
layout: post
title: "Set git configuration variables"
date: 2024-10-25
Categories: git
permalink: /:title
---

```sh
git config --global user.name "username"
git config --global user.email "user@email.com"
git config --global user.password "TOKEN"
git config --global core.editor "vim"
```

To see the Git configures do:

```sh
git config --list
```

Use crediential helper so that Git does not ask for username and password (token) every time.

```sh
git config --global crediential.helper cache
```

To unset the above (e.g., using a new token) do:

```sh
git config --global --unset crediential.helper
```

