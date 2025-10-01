---
created: 2024-03-12T20:52
updated: 2024-03-12T21:13
---
#language/python 
kv store in python

## valid keys
> "anything hashable"
> for a class to be hashable, it should have a `__hash__()` method

classes are by default given `__hash__()` which uses the object's memory address unless overload `__eq__()`