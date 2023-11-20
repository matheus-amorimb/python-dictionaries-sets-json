# Dictionaries

## Creating Dictionaries

Basic structure of dictionary elements: {key : value}

value -> any Python object
key -> any hashable object

| Hashable Objects                                             |
| ----------------------------------------------- | ------------ |
| set, dictionary                                 | not hashable |
| list                                            | not hashable |
| custom classes and objects                      | maybe        |
| tuples (only if all elements are also hashable) | hashable     |
| int, float, complex, binary, Decimal            | hashable     |
| strings                                         | hashable     |

important: two objects that do not compare equal may still have the same hash (hash collision). More hash collisions, slower dictionaries.

```python
#Literals
{
    'john': ['John', 'Clees', 78],
    (0, 0): 'origin',
    'repr': lambda x: x **2,
    'eric': {'name': 'Matheus',
             'age': 25}
}

#Constructor
#key must be a valid identifier name, in this case dictionary key will then be a string og that name
dict(
    john = ['John', 'Clees', 78],
    repr = lambda x: x **2,
    eric = {'name': 'Matheus',
            'age': 25},
    twin = dict(name = 'Matheus', age = 25)
)

#Comprehensions
{f'key_{str(i)}': i**2 for i in range(1, 5)}


#Not pythonic way
d = {}
for i in range(1, 5):
    key = f'key_{i}'
    d[key] = i**2

print(d)


#fromkeys()
##creates a dictinary with specified keys all assigned the same value
##iterable contains the keys, hashable elements
d = dict.fromkeys([i**2 for i in range(1, 5)], False)
print(d)

```

## Commom Operations
## Dictionary Views
## Updating, Merging and Copying
## Custom Classes and Hashing