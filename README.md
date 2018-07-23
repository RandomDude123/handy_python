## This is a collection of useful python code snippets i stumbled on.

### remove whitespaces from string
```python
test_str = 'a\n\t  b\n\t             c'
' '.join(test_str.split())
>>> 'a b c'
```

### use start-argument in enumerate
```python
letters = 'abcde'
for i, letter in enumerate(letters, start=1):
    print(i, letter)
```

### use f-strings
```python
x = 10

# exception message example
raise ValueError(f"Expected {x!r} to a float not a {type(x).__name__}")

# formatting still works the same
print(f'This is a print of x with leading 0s: {x :08d}')

# even code runs inside { }
print(f'This is a print of x with leading 0s: {x ** 2 :08d}')
```

### Error handling & logging
```python
import sys
import logging

def error_handling(em):
    # (type, value, traceback)
    return f'{em[0]}. {em[1]}, line: {em[2].tb_lineno}'

try:
    x = 1 / 0
except Exception as e:
    logging.error(error_handling(sys.exc_info()))
```

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
>>> {0: 'a', 1: 'b', 2: 'c'}

# better in terms of speed
index_dict =  {i: elem for i, elem in enumerate(elem_list)}

# index as value and elem as key of the dict
elem_index_dict = {elem: i for i, elem in enumerate(elem_list)}
>>> {'a': 0, 'b': 1, 'c': 2}
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
>>> a 3
>>> b 2
>>> c 1
```

### Dump json to file:
```python
import json
with open('data.json', 'w') as f:
    json.dump(data, f)
```

> Tested with Python 3.6.3.

> All performance related statements are based on comparing execution times with `%timeit` on my personal computer.
