---
layout: post
title:  "My tmux cheatsheet"
tags: commandline
---

If you often work on a remote server, then probably you should give [tmux](https://tmux.github.io) a try.

Here is what I often do when I open my MacBook Pro for work:
1. Open ```iTerm2``` and ```ssh``` to the remote server that I am working on;
2. ```tmux attach``` to the session where I leave off yesterday;
3. I can continue my work instantly.

Below are my most frequently used  commands. List them here for a quick reference.

### session

operation | command
--- | ---
create | tmux new -s test
show | C-b s
| tmux ls
detach | C-b d
| tmux detach
attach | tmux a -t test
kill | tmux kill-session -t test
rename | C-b $
| tmux rename-session -t test test2

### window

operation | command
--- | ---
create | C-b c
rename | C-b ,
next | C-b n
previous | C-b p
go to | C-b <number>
list | C-b w

### pane

operation | command
--- | ---
create horizontally | C-b "
create vertically | C-b %
show number | C-b q
togger panes | C-b o
swap panes | C-b {
| C-b }
move | C-b h
| C-b j
| C-b l
| C-b k
kill | C-b x
break to window | C-b !

### Ask for more?
```C-b ?```
