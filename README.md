```python
from dataclasses import dataclass
from typing import Tuple


class Meta(type):
    def __new__(cls, name, bases, attrs):
        new_cls = super().__new__(cls, name, bases, attrs)
        return dataclass(unsafe_hash=True, frozen=True)(new_cls)


class Bio(metaclass=Meta):
    name        : str = "SharkSV"
    designation : str = "Software Engineer"
    company     : str = "Hy inc."
    base        : str = "Beirut, Lebanon"


class Stack(metaclass=Meta):
    languages   : Tuple[str, ...] = ("C#", "C++", "Js", "Java", "Python")
    databases   : Tuple[str, ...] = ("MySQL", "Mongo", "Redis")
    misc        : Tuple[str, ...] = ("Docker")


class Social(metaclass=Meta):
    twitter     : str = "iTzSharkSV"
    discord     : str = "iTzShark#0690"
```
