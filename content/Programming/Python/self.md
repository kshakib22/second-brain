In Python, when you define a method within a class, the first parameter is conventionally named `self`. This parameter implicitly refers to the instance of the class that the method is being called on. 
Abstract ideas to relate - `itself` or `this` 

`self` is how methods can access and modify the attributes and other methods of the object they belong to. 


> [!warning] Methods with/without self
> Any normal method *must* take self as the first parameter. Exceptions are [[stratic method]] and [[class method]]. 

For example: 

```python
class MyClass:
    def my_method():  # Missing 'self' parameter
        print("This is a method")
# Attempt to create an instance and call the method
obj = MyClass()
obj.my_method()
```

This code will produce `TypeError: my_method() takes 0 positional arguments but 1 was given`


