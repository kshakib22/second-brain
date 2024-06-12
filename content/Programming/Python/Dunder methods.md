Dunder (Double under) methods are special methods in Python starting and ending with double underscores `__`. These are also known as '[magic methods](Dunder%20methods.md)'.  There are many dunder methods, but add them as you learn about them.

- **`__init__(self, ...)`** : The constructor method, called when you create an object of a class. It's used to initialize the object's attributes.
- **`__str__(self)`** : Defines how your object is represented as a string. Called when you use `str(object_name)` :  Allows custom output of an object when printed.
- `__main__` :  Separates all code from the main part. All the functions in this `.py` file can be imported into other files without the `main` . If this particular file is run, then `main` will also run.