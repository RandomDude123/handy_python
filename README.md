## This is a collection of useful python code snippets i stumbled on.

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
