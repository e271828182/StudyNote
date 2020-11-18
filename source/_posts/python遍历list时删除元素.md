---
title: python遍历时删除元素
date: 2020-11-18 14:41:05
tags: python
categories: python
---

在集合元素遍历期间，删除元素要注意（在java中可以用Iterator来删除）

<!--more-->

因遍历过程中下标时增长的，删除后list变短，元素位置会左移，导致部分元素遍历时遗漏处理的情况（<span style="color:red">但是不会抛出异常</span>）

解决方案有三个

1. 不在遍历时移除数据，用其他方式实现逻辑
2. 用浅拷贝遍历
3. 倒序删除

```python
import copy
def test(data):
    # data2 = data  # 不拷贝 - 结果出错，无异常抛出
    data2 = [x for x in data]  # 浅拷贝
    # data2 = data.copy()  # 浅拷贝
    # data2 = copy.deepcopy(data)  # 深拷贝 - 出错，抛出异常，移除时找不到元素
    # data2 = copy.copy(data)  # 浅拷贝
    for i in data2:
        print(i)
        data.remove(i)
    return data

# 倒序删除举例
# def test2(data):
#     for i in data[::-1]:
#         print(i)
#         data.remove(i)
#     return data

class A(object):
    def __init__(self, v):
        self.value = v

    def __repr__(self):
        return self.value

d = [A(x) for x in list('ABCD')]
print(test(d))
```

