---
layout: post
title:  "Test discovery and XUnit style setup/teardown in pytest"
tags: python
---

Here is a sample test file `test_file.py` to show how test discovery and setup/teardown work in pytest.

```
def setup_module(module):
    print("\nsetup module")


def teardown_module(module):
    print("\nteardown module")


def setup_function(function):
    if function == test1:
        print("\nsetup test1")
    elif function == test2:
        print("\nsetup test2")
    else:
        print("\nsetup unknown function")


def teardown_function(function):
    if function == test1:
        print("\nteardown test1")
    elif function == test2:
        print("\nteardown test2")
    else:
        print("\nteardown unknown function")


def test1():
    print("\nin test1")
    assert True


def test2():
    print("\nin test2")
    assert True


class TestClass:
    @classmethod
    def setup_class(cls):
        print("\nSetup TestClass")

    @classmethod
    def teardown_class(cls):
        print("\nteardown TestClass")

    def setup_method(self, method):
        if method == self.test1:
            print("\nsetup class test1")
        elif method == self.test2:
            print("\nsetup class test2")
        else:
            print("\nsetup unknown method")

    def teardown_method(self, method):
        if method == self.test1:
            print("\nteardown class test1")
        elif method == self.test2:
            print("\nteardown class test2")
        else:
            print("\nteardown unknown method")

    def test1(self):
        print("\nin class test1")
        assert True

    def test2(self):
        print("\nin class test2")
        assert True
```

### Test discovery
Run following command, and you can see `pytest` collects the four test cases automatically:
```
$ pytest --collect-only
collected 4 items
<Module 'test_sample.py'>
  <Function 'test1'>
  <Function 'test2'>
  <Class 'TestClass'>
    <Instance '()'>
      <Function 'test1'>
      <Function 'test2'>
```

### Setup/teardown
Run following command, and you can see how the setup/teardown functions are run for modules, functions, classes and methods in classes.
```
test_sample.py::test1
setup module

setup test1

in test1
PASSED
teardown test1

test_sample.py::test2
setup test2

in test2
PASSED
teardown test2

test_sample.py::TestClass::test1
Setup TestClass

setup class test1

in class test1
PASSED
teardown class test1

test_sample.py::TestClass::test2
setup class test2

in class test2
PASSED
teardown class test2

teardown TestClass

teardown module
```
