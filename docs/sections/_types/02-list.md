---
title: List
slug: list
layout: section
date: 2020-10-01
---

**Contents**

- [Basics](#basics)
- [Reverse a list](#reverse-a-list)
- [Further reading](#further-reading)

## Basics

A list is used to group values together. It is written as a pair of square brackets containing comma-separated items. For example, a list of five integers is shown below. Lists can contain items of different types.

```python
>>> mylist = [1, 2, 3, 4, 5]
>>> mylist
[1, 2, 3, 4, 5]
```

Indexing returns an item from a list.

```python
# return the first item
>>> mylist[0]
1

# return the second item
>>> mylist[1]
2

# return the last item
>>> mylist[-1]
5

# return the second to last item
>>> mylist[-2]
4
```

Slicing returns a new list from items in the original list.

```python
>>> mylist[1:]
[2, 3, 4, 5]

>>> mylist[1:3]
[2, 3]
```

New items can be added to the end of a list using the append function.

```python
>>> mylist.append(9)
>>> mylist
[1, 2, 3, 4, 5, 9]
```

Items in a list can be unpacked using comma separated variables. An `*` allows several variables to be unpacked into a single variable.

```python
# unpack items in a list
>>> a, b, c, = [8, 9, 10]
>>> a
8
>>> b
9
>>> a, b, c
(8, 9, 10)

# unpack several items into a single variable
>>> first, *rest = [1, 2, 3, 4, 5, 6, 7]
>>> first
1
>>> rest
[2, 3, 4, 5, 6, 7]

# unpack middle items into a variable
>>> first, *mid, last = [1, 2, 3, 4, 5, 6, 7]
>>> first
1
>>> mid
[2, 3, 4, 5, 6]
>>> last
7
```

The enumerate function returns the index and the associated item from a list.

```python
>>> letters = ['a', 'b', 'c', 'd', 'e']
>>> for i, x in enumerate(letters):
...     print(f'index = {i} and letter = {x}')
...
index = 0 and letter = a
index = 1 and letter = b
index = 2 and letter = c
index = 3 and letter = d
index = 4 and letter = e
```

The zip function can be used to iterate over two or more lists.

```python
>>> one = [1, 2, 3, 4, 5]
>>> two = [2, 3, 4, 5, 6]
>>> three = [3, 4, 5, 6, 7]
>>> for i, j, k in zip(one, two, three)
...     print('i', i, 'j', j, 'k', k)
...
i 1 j 2 k 3
i 2 j 3 k 4
i 3 j 4 k 5
i 4 j 5 k 6
i 5 j 6 k 7

# or use index to get each item from multiple lists
>>> n = len(one)
>>> for i in range(n):
...     print('i', one[i], 'j', two[i], 'k', three[i])
...
i 1 j 2 k 3
i 2 j 3 k 4
i 3 j 4 k 5
i 4 j 5 k 6
i 5 j 6 k 7
```

## Reverse a list

There are several ways to reverse items in a list. The first approach is to reverse the list in-place. This is fast and does not take up extra memory but it modifies the original list.

```python
# reverse a list in-place
>>> list_one = [1, 2, 3, 4, 5]
>>> list_one.reverse()
>>> list_one
[5, 4, 3, 2, 1]
```

Slicing creates a reversed copy of the list. This takes up memory but doesn't modify the original list.

```python
# create a reversed copy of a list
>>> list_two = [6, 7, 8, 9, 10]
>>> list_three = list_two[::-1]
>>> list_three
[10, 9, 8, 7, 6]
```

The reversed function returns an iterator that returns elements in reverse order. This does not modify the original list but the result needs to be converted into a new list object.

```python
# return elements in reverse order then convert to a new list
>>> list_four = [11, 12, 13, 14, 15]
>>> list_five = list(reversed(list_four))
>>> list_five
[15, 14, 13, 12, 11]
```

## Further reading

- An Informal Introduction to Python — Python 3.8.6rc1 Documentation. Accessed September 16, 2020. <https://docs.python.org/3/tutorial/introduction.html#lists>