---
layout: post
title:  "Cheatsheet for Buffers, Windows and Tabs of Vim"
tags: vim
---

My cheatsheet to operate the bufers, windows and tabs of Vim.

## Buffers
- ```:badd```: buffer add
- ```:ls```: list buffer<br/>
  buffer indicators:
  - ```%```: buffer in current window
  - ```a```: active buffer
  - ```#```: alternate buffer, which can be accessed by ```Ctrl-6```
  - ``` ```: no indicator means that buffer is not loaded yet
- ```:bp```: load ***previous*** buffer into current window
- ```:bn```: load ***next*** buffer into current window
- ```:b2```: load buffer No. 2 into current window
- ```:br```: ***rewind*** first buffer into current window 
- ```:bl```: load ***last*** buffer into current window
- ```:ba```: open ***all*** buffers into different windows
- ```:bd```: ***delete*** buffer, take buffer number as arguments, ```:bd 1 2 3```

## Windows
- ```vim -o file1.txt file2.txt```: open files in two horizotally split window
- ```vim -O file1.txt file2.txt```: open files in two vertically split window
- ```:sp file.txt```: open file as horizontal split
- ```:vs file.txt```: open file as vertical split
- ```:n file.txt```: ***new*** a file in current window
- ```Ctrl-w n```: ***new*** a file in horizontal split, ```:w file.txt``` for saving
- ```:vne file.txt```: ***new*** a file in vertical split
- ```Ctrl-w h/j/k/l```: switch window

- ```Ctrl-w H/J/K/L```: move window
- ```Ctrl-w T```: move current window to a new tab
- ```Ctrl-w r```: rotates the windows from left to right or from top to bottom
- ```Ctrl-w R```: rotates the windows from the other direction

- ```Ctrl-w =```: resize the windows equally
- ```Ctrl-w >```: incrementally increase the window to the right, takes a parameter, e.g. ```Ctrl-w 20 >```
- ```Ctrl-w <```: incrementally increase the window to the left
- ```Ctrl-w -```: incrementally decrease the window's height
- ```Ctrl-w +```: incrementally increase the window's height
- ```Ctrl-w _```: maximize the window's height

## Tabs
- ```vim -p file1.txt file2.txt```: open files in separate tabs
- ```:tabnew file.txt```: open file.txt in a new tab
- ```:tabc```: ***close*** current tab
- ```:tabn```: go to ***next*** tab
- ```:tabn 2```: go to tab No. 2
- ```:tabp```: go to ***previous*** tab
- ```:tabr```: ***rewind*** to first tab
- ```:tabl```: go to ***last*** tab

