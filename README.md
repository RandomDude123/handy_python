## This is a collection of useful python code snippets i stumbled on.

Create a dict of a list mapping the index of an element as key to the value:
```python
elem_list = ['a', 'b', 'c']
index_dict = dict(enumerate(elem_list))
# {0: 'a', 1: 'b', 2: 'c'}

# index as value of the dict and elem as key
elem_index_dict = {elem: i for i, elem in enumerate(elem_list)}
# {'a': 0, 'b': 1, 'c': 2}
```

Flatten list of lists:
```python
parent_list = [['a', 'b', 'c'], [1, 2, 3]]
flat_list = [elem for child_list in parent_list for elem in child_list]

# better in terms of speed
flat_list = sum(parent_list, [])
```

Counting with a dict:
```python
elem_list = ['a', 'b', 'c', 'a', 'b', 'a']

cnt = {}
for elem in elem_list:
    cnt[elem] = cnt.get(elem, 0) + 1


for k, v in sorted(cnt.items()):
    print(k, v)
# a 3
# b 2
# c 1
```
