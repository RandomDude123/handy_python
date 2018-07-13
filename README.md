## This is a collection of useful python code snippets i stumbled on.

### Use format() in different ways
```python
class exampleClass:
    def __init__(self, a, b, c):
        self.a = a
        self.b = b
        self.c = c
        
example = exampleClass(1, 'hello', 1.234)

print('{e.a} and {e.b} and {e.c}'.format(e=example))

# even cooler
print(f'{example.a} and {example.b} and {example.c}')
```

### Create a dict of a list mapping the index of an element as key to the value:
```python
elem_list = ['a', 'b', 'c']
index_dict = dict(enumerate(elem_list))
# {0: 'a', 1: 'b', 2: 'c'}

# better in terms of speed
index_dict =  {i: elem for i, elem in enumerate(elem_list)}

# index as value and elem as key of the dict
elem_index_dict = {elem: i for i, elem in enumerate(elem_list)}
# {'a': 0, 'b': 1, 'c': 2}
```

### Flatten list of lists:
```python
parent_list = [['a', 'b', 'c'], [1, 2, 3]]
flat_list = [elem for child_list in parent_list for elem in child_list]

# better in terms of speed
flat_list = sum(parent_list, [])
```

### Counting with a dict:
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

### Dump json to file:
```python
import json
with open('data.json', 'w') as f:
    json.dump(data, f)
```

> For Python 3.6.3.

> All performance related statements are based on comparing execution times with `%timeit` on my personal computer.
