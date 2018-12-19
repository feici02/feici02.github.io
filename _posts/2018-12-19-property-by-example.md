---
layout: post
title:  "Decorator @property by example"
tags: python
---

@property is a Pythonic way to write the setter/getter for a member variable of a class.

## Sample
`_temperature` is the inernal variable exposed as `temperature`. 
```
class Celsius:
    def __init__(self, value = 0):
        self._temperature = value

    def to_fahrenheit(self):
        return (self._temperature * 1.8) + 32

    @property
    def temperature(self):
        return self._temperature

    @temperature.setter
    def temperature(self, value):
        if value < -273:
            raise ValueError("Temperature below -273 is not possible")
        self._temperature = value
```

## Run

```
>>> from celsius import Celsius
>>> c = Celsius(10)
>>> c.temperature
10
>>> c.temperature = 20
>>> c.temperature
20
>>> c.to_fahrenheit()
68.0
```

## Reference
- https://www.programiz.com/python-programming/property
