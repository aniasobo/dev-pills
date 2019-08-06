# Underscores in method names

`__foo__`: this is just a convention, a way for the Python system to use names that won't conflict with user names.

`_foo`: this is just a convention, a way for the programmer to indicate that the variable is private (whatever that means in Python.

`__foo:` this has real meaning: the interpreter replaces this name with `_classname__foo` as a way to ensure that the name will not overlap with a similar name in another class.


from [StackOverflow](https://stackoverflow.com/questions/1301346/what-is-the-meaning-of-a-single-and-a-double-underscore-before-an-object-name)