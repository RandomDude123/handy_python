## This is a collection of useful python code snippets i stumbled on.

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
>> a 3
>> b 2
>> c 1
```
