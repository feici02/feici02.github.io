---
layout: post
title:  "A very simple decorator"
tags: python
---

A very simple decorator sample for future reference.

## Sample code

decorator-sample.py
```Python
def star(func):
    def inner(*args, **kwargs):
        print("*" * 20)
        func(*args, **kwargs)
        print("*" * 20)
        print()
    return inner

@star
def hello(name="world"):
    print(f"Hello, {name}!")

if __name__ == "__main__":
    hello()
    hello("Python")
```

## Output
```
$ python3 decorator-sample.py
********************
Hello, world!
********************

********************
Hello, Python!
********************

```
