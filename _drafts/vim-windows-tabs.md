## Buffer
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


## Open multiple files in two horizotally split window
vim -o file1.txt file2.txt

## Open multiple files in two vertically split window
vim -O file1.txt file2.txt

## Open multiple files in separate tabs
vim -p file1.txt file2.txt file3.txt

## tab related commands
```
# open file.txt in a new tab
:tabnew file.txt

# close current tab
:tabc

# go to next tab
:tabn

# go to the second next tab
:tabn 2

# go to previous tab
:tabp

# go to the first tab (rewind)
:tabr

# go to the last tab
:tabl
```
