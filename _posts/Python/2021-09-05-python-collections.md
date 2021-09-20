---
layout: post
title: "Python Collections"
subtitle: "Python Collections 模块"
date: 2021-09-05
author: "Seeyou"
header-img: "img/post-bg-2015.jpg"
abstract: "collections 是 python 的一个基础工具库"
tags: [Python, Module, Query]
---

## Usage

> defaultdict, 带默认值不会报错的字典

```py
from collections import defaultdict
data = [(1, 3), (2, 1), (1, 4), (2, 5), (3, 7)]
d = defaultdict(list) # 规定字典的元素为列表

for k, v in data:
    d[k].append(v)
```

> Counter, 数数和排序

```py
from collections import Counter
words = ['apple', 'apple', 'pear', 'watermelon', 'pear', 'peach']
counter: Counter = Counter(words)
counter.most_common(n=2)  # n,topk -> list

# 直接从字典构造 Counter
c: Counter = Counter({'apple': 5, 'pear': 4})
c: Counter = Counter(apple=4, pear=3)

# 常用方法
sum(c.values()) # 算值
c.clear() # reset all counts
list(c) # list unique elements
```

> deque, 双端队列

使用deque主要有两个原因:
- 第一个原因是 deque 收到GIL的管理，它是线程安全的。而list则没有GIL锁，因此不是线程安全的。也就是说在并发场景下，list可能会导致一致性问题，而deque不会。

- 另一个原因是deque支持固定长度，当长度满了之后，当我们继续append时，它会自动弹出最早插入的数据。

我们拥有海量的数据，我们不知道它的数量，但是想要保留最后出现的指定数量的数据的时候，就可以使用deque

```py
from collections import deque
dque = deque(maxlen=10)
# 假设我们想要从文件当中获取最后10条数据
dque.append(x)
dque.appendleft(x)
dque.copy() # 浅拷贝
dque.count(x) # 计算 deque 中元素等于 x 的个数
dque.extend(iterable) # 扩展deque的右侧
dque.extendleft(iterable) # 拓展右侧
dque.index(x[, start[, stop]])
dque.pop()
dque.popleft()
dque.reverse()
dque.rotate(n=1)
dque.maxlen
```

> namedtuple, 元编程

```py
from collections import namedtuple
# 需要一行就定义了一个类, 默认参数右对齐
Student = namedtuple('Student', ['name', 'score', 'age'], defaults=(0, 0))
```

## Reference

[Python——详解collections工具库](https://zhuanlan.zhihu.com/p/110476502)

[Python Docs](https://docs.python.org/zh-cn/3/library/collections.html)