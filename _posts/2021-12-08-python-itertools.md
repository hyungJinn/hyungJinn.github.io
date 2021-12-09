---
title: "Python: itertools - Combinatoric iterators"

categories:
  - Python
  - Module
tags:
  - Itertools

search: true
comments: true
---

> Python

[itertools - Functions creating iterators for efficient looping](https://docs.python.org/3/library/itertools.html)

### 개념

iterator(반복자)

Combinatoric iterators
| iterator | Arguments | Results |
| :-: | :-: | :-: | :-: | :-: |
| product() | p, q, ... repeat = 1 | |
| permutations() | p[, r] | |
| combinations() | p, r | |
| combinations_with_replacement() | p, r | |

| Examples | Results |
| :-: | :-: |
| product('ABCD', repeat=2) | `AA AB AC AD BA BB BC BD CA CB CC CD DA DB DC DD` |
| permutations('ABCD', 2) | `AB AC AD BA BC BD CA CB CD DA DB DC` |
| combinations('ABCD', 2) | `AB AC AD BC BD CD` |
| combinations_with_replacement('ABCD', 2) | `AA AB AC AD BB BC BD CC CD DD` |

```python
print(list(itertools.combinations([0, 1, 2, 3, 4, 5], 1)))
print(list(itertools.combinations(range(6), 1)))
# output: [(0,), (1,), (2,), (3,), (4,), (5,)]
```