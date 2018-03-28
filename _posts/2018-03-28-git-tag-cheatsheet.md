---
layout: post
title:  "My Cheatsheet for git tag"
tags: git
---

Commands related to the `tag` subcomamnd of `git`.

* show available tags
```
git tag
```
* create a non-annonated (a.k.a. lightweight) tag (without metadata)
```
git tag temp
```
* create an annonated tag (with metadata)
```
git tag -a v1 -m "release v1.0"
```
* show info about a tag
```
git show v1
```
* show the diff between HEAD and the nearest previous tag
```
git describe
```
* push all the local tags to remote (`git push` will not push tags by default)
```
git push --tags
```
* push a single tag
```
git push origin v1
```
* fetch all tags associate with current branch
```
git pull
```
* fetch all tags
```
git fetch --tags
```
* checkout to a tag
```
git checkout v1
```
* checkout to the last commit of a branch (e.g.: master)
```
git checkout master
```
* delete a tag
```
git tag -d v1
```
