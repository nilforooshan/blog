---
layout: post
title: "git cheat sheet"
date: 2024-10-25
Categories: git
permalink: /:title
---

Clone a repository

```sh
git clone <sourse>
```

Clone a specific branch of a repository

```sh
git clone -b <branch> <sourse>
```

Create a local repository

```sh
git init
```

See the changed files since the last commit

```sh
git status
```

Add/remove all the current changes to the next commit

```sh
git add .
```

Commit the changes

```sh
git commit -m "message"
```

Give commit extra description

```sh
git commit -m "message

Description"
```

See the changes to the tracked files

```sh
git diff
```

Compare a file between two branches

```sh
git diff mybranch master -- myfile.cs
```

See the log of the commited changes, starting from the most recent

```sh
git log
```

See the log of the commited changes for a specific file

```sh
git log -p <filename>
```

Discard the last commit

```sh
git reset --hard HEAD^
```

Discard the last 2 commits

```sh
git reset --hard HEAD^^
```

Reset to a specific commit and discard the more recent commits

```sh
git reset --hard <commit ID>
```

Discard the last commit, but preserving the changes as unstaged changes

```sh
git reset HEAD^
```

There is also `git revert` for reverting back to a previous commit.
It will undo changes up to the state before the specified commit ID.
`git revert` is a new commit of a previous commit.
It does not discard the latest commits.
I found this useful:

```sh
git revert <commit ID> # We are interested in the commit before this one!
# View the files.
git reset --hard HEAD^ # Discard the previous revert (commit).
```

This way is even better:

```sh
git checkout <previous commit ID>
git switch - # Get back to the commit from which you checked out to <previous commit ID> (latest commit).
```

Updating local files by downloading the latest changes

```sh
git pull <remote> <branch>
```

Note that `git pull` is equivalent to `git fetch && git merge`.

Add a remote to a local repository

```sh
git remote add origin https://github.com/<user>/<repo>.git
```

Update the remote address (change of repository name) in a local repository

```sh
git remote set-url origin https://github.com/<user>/<repo>.git
```

To verify the remote:

```sh
git remote -v
```

Push local changes to a remote

```sh
git push -u origin master
```

List the existing branches; the current one is highlighted

```sh
git branch
```

Create a new branch from the HEAD of the curent branch

```sh
git branch <branchname>
```

Note that `git checkout -b <new-branch>` is equivalent to `git checkout -b <new-branch> <existing-branch>` and `git branch <new-branch> && git checkout <new-branch>`.

Check-out from the current branch and check-in to a new branch

```sh
git checkout <branchname>
```

Alternatively, use

```sh
git switch <branch>
```

Optionally a new branch could be created with either `-c` or `-C` options.

Moving to the master branch and merge the new branch with the master branch

```sh
git checkout master
git merge <branchname>
```

Delete a branch

```sh
git branch -d <branchname>
```

Use tags to assign milestones such as v1, v1.1 and v2 to a commit. You may have one or multiple tags on a branch.

List tags

```sh
git tag
```

Add a tag to the last commit

```sh
git tag <tagname>
```

Push tags to GitHub

```sh
git push --tags
```

Delete a tag locally

```sh
git tag -d <tagname>
```

Delete a locally deleted tag on GitHub

```sh
git push origin :<tagname>
```

Remove files that are not under version control

```sh
git clean -f -q
```

To undo the effects of `git add` and unstage the staged changes, use `git restore`. Examples are:

```sh
git restore index.html # Undo the added cahnges to index.html
git restore --staged index.html # Undo staged changes to index.html
git restore --source 7173808e index.html # Restore index.html to the #7173808e commit
```

Discard uncommitted changes to the README file

```sh
git checkout README
```

Forgot to make a small change and made a commit?
You can amend to the last commit (make changes to the last commit without making a new commit)

You can use the same command to change the commit message.
If you have already pushed the commit to GitHub.com, you will have to force push a commit with an amended message (`git push --force-with-lease origin BRANCHNAME`).

```sh
git commit --amend -m "MESSAGE"
```

Get rid of the deleted branches

```sh
git remote prune origin
```

