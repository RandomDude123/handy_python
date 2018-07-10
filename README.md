## This is a collection of useful python code snippets i stumbled on.

Counting with a dict:
```
cnt = {}
for elem in elem_list:
  cnt[elem] = cnt.get(elem, 0) + 1
```
