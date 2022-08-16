# Python Data Structures cheatsheet

## Table of Contents
1. **[List](#list)**  
1.1. **[Stack](#stack)**  
2. **[Set](#set)**  
3. **[Dict](#dict)**  
3.1. **[Counter](#counter-bag)**  
4. **[Queue](#queue)**  
5. **[Priority Queue](#priority-queue)**


## List

```Python
a = []
#  or 
a = list()
```

| Operation | Example | Complexity |
|-----------|---------|------------|
| Add elem  | `a.append(x)` | O(1)   |
| Extend | `a.extend(iterable)` | O(k)  |
| Insert elem x into i-th pos | `a.insert(i, x)` | O(n)  |
| Remove elem x | `a.remove(x)`    | O(n)  |
| Pop last elem | `a.pop()` | O(1) |
| Pop i-th elem | `a.pop(i)` | O(n) |


### Stack
Use list with `append(x)` and `pop()`. Example:
```Python
stack = [3, 4, 5]
stack.append(6)
stack.append(7)

stack        # [3, 4, 5, 6, 7]
stack.pop()  # 7
stack        # [3, 4, 5, 6]
```

## Set
```Python
s = set(iterable)
#  or 
s = set()
```

| Operation | Example | Complexity |
|-----------|---------|------------|
| Membership test | `x in s` | O(1) [Worst case: O(n)]|
| Add elem  | `s.add(x)` | O(1) [Worst case: O(n)]  |
| Remove elem x | `s.remove(x)`  or `s.discard(x)`   | O(1) [Worst case: O(n)] |
| Pop arbitrary elem | `s.pop()` | O(1) |
| Subset check | `s1.issubset(s2)` | |
| Union | `s1.union(s2)` | O(len(s1)+len(s2)) |
| Intersection | `s1.intersection(s2)` | O( min(len(s1), len(s2)) ) [Worst case: O(len(s1) * len(s2))] |
| Difference | `s1.difference(s2)` or `s1.symmetric_difference(s2)` | O(len(s1)) [Worst case: O(len(s1) * len(s2)) ] |


## Dict
```Python
d = {}
#  or 
d = dict()
```

| Operation | Example | Complexity |
|-----------|---------|------------|
| Membership test | `k in d` | O(1) [Worst case: O(n)]|
| Set item  | `d[k] = v` | O(1) [Worst case: O(n)] |
| Set item  | `d[k]` or `d.get(k)` | O(1) [Worst case: O(n)] |
| Remove elem x | `del d[k]`  or `d.pop(k)`   | O(1) [Worst case: O(n)] |
| Iterate | `for k, v in d.items()` or `for k in d.keys()` or `for v in d.values()` | O(n) | 

## Counter (Bag)
```Python 
from collections import Counter

c = Counter([1, 2, 2, 3, 1, 1, 1, 3, 2])
# or
c = Counter(a=4, b=2, c=0, d=-2) 

```
| Operation | Example | Complexity |
|-----------|---------|------------|
| Most common | `c.most_common(k)` | |
| Sum of all elem counts | `c.total()` | O(n) |
| Subtract | `c1.subtract(c2)` | O(len(c2)) |
| Iterate over elements | `for elem in d.elements()` | O(n) | 

## Queue

```Python
from collections import deque

q = deque(["Eric", "John", "Michael"])
```

| Operation | Example | Complexity | 
|-----------|---------|------------|
| Add elem  | `q.append(x)` or `q.appendleft(x)` | O(1) |
| Pop  elem | `q.pop()`  or `q.popleft()`        | O(1) |
| Rotate    | `q.rotate(k)`                      | O(k) |
| Extend    | `q.extend(iterable)`  or `q.extendleft(iterable)` | O(k) |
| Insert elem x into i-th pos | `q.insert(i, x)` | O(n)  |
| Get index of elem | `q.index(x)` | O(n)  |
| Remove elem x | `q.remove(x)`    | O(n)  |



## Priority Queue

```Python
import heapq

h = [5, 7, 9, 1, 3]
heapq.heapify(h)
h                      # [1, 3, 9, 7, 5]
heapq.heappop(h)       # 1
h                      # [3, 5, 9, 7]
heapq.heappush(h, 4)   # 
h                      # [3, 4, 9, 7, 5]

# or 
```

| Operation | Example | Complexity | 
|-----------|---------|------------|
| Create heap | `heapify(h)` | O(n) |
| Get min element | `h[0]` | O(1) |
| Add elem  | `heappush(h, x)` | O(log(n)) |
| Pop  min elem | `heappop(h)`     | O(log(n)) |
| Push and pop |`heappushpop(h, x)`| O(log(n)) |
| Pop and push |`heapreplace(h, x)`| O(log(n)) |

