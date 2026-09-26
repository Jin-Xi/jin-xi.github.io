---
title: "Python 中的 isinstance 和 type"
description: "梳理 Python 中 isinstance() 与 type() 的差异，以及子类判断的边界。"
date: 2023-02-08T01:10:17+08:00
tags: ["Python", "类型系统"]
type: tech
draft: false
path: "2023/02/08/python1"
---

## `isinstance()` 函数

`isinstance()` 是 Python 内置函数，用来判断一个对象是否是某个类或子类的实例，返回 `True` 或 `False`。

```python
isinstance(object, classinfo) -> bool
```

- `object`：实例对象。
- `classinfo`：可以是类、基本类型，或它们组成的元组。

## `type()` 函数

`type()` 返回对象的具体类型。

```python
class A:
    pass

class B(A):
    pass

print(isinstance(A(), A))  # True
print(type(A()) == A)      # True
print(isinstance(B(), A))  # True
print(type(B()) == A)      # False
```

`isinstance()` 会考虑继承关系；`type(x) == A` 只判断对象的具体类型是否恰好为 `A`。
