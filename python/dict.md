# Data types - dictionaries in python <!-- omit in toc -->

Syntax: `{"key": "value", "another_key": "another_value"}`

**Keys:**

* have to be unique
* have to be immutable
  * can only be tuples if they contain immutable objects: strings, numbers and other tuples
  * lists can't be keys because they're mutable
     
- [Accessing values](#accessing-values)
- [Add key-value pair](#add-key-value-pair)
- [Modify a key-value pair](#modify-a-key-value-pair)
- [Delete a key-value pair](#delete-a-key-value-pair)
- [Check for key presence](#check-for-key-presence)
- [Check value presence](#check-value-presence)
- [Count key-value pairs](#count-key-value-pairs)
- [Iterating over python dictionaries](#iterating-over-python-dictionaries)
- [Dictionary methods](#dictionary-methods)
  - [.clear()](#clear)
  - [.get()](#get)
  - [.pop()](#pop)
  - [.update()](#update)
  - [More python dictionary methods](#more-python-dictionary-methods)

---

## Accessing values

`dogs = {"Bear": "good dog", "Moose": "not so good"}`

To access the rating: `dogs["Bear"]`
    
```
<variable>[<key>]
```

## Add key-value pair

```
dogs["Noodles"] = "average dog"
```

## Modify a key-value pair

```
dogs["Moose"] = "good dog"
```

## Delete a key-value pair

```
del dogs["Noodles"]
```

## Check for key presence

```
"Bear" in dogs
```

Will return `True` or `False`, not the key value.

## Check value presence

```
"good dog" in dogs.values()
```

Will return a boolean.

## Count key-value pairs

```
len(dogs)
```

## Iterating over python dictionaries

```
# iterate over keys

for dog in dogs:
  print(dog)  # prints the keys
```
    
```
# iterate over key-value pairs

for <key-value-pair-as-tuple> in <dictionary>.items():
	# Do this

# in code

for pair in dogs.items():
  print(pair) # prints (key, value)
```
    
```
# assign keys and values to variables

for key, value in dogs.items():
  print("Key:", key, "; Value:", value)
```

```
# iterate over the values

for rating in dogs.values():
  print(rating)
```

## Dictionary methods

### `.clear()`

Removes all key-value pairs in a dictionary.

`dogs.clear()`

### `.get()`

`.get(<key>, <default>)` returns the value associated with the key, or the default passed in as second argument if value not present.

### `.pop()`

`.pop(<key>, <default>)` 

1. removes the key-value pair from the dictionary
2. returns the value

### `.update()`

`.update(<another dict>)`

Replaces the values of a dictionary with the values of another dictionary but only for keys that exist in both.

```
dogs = {"Bear": "good dog", "Moose": "nice boy", "Noodle": "average dog"}
new_dogs = {"Bear": "no good dog"}
dogs.update(new_dogs)
dogs
{'Bear': "no good dog", 'Moose': "nice boy", 'Noodle': "average dog"}
```

### More python dictionary methods

[Look in the docs](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)

