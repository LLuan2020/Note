## Encapsulation

- **What is encapsulation?**

    Encapsulation is the packing of data and functions that work on that data within a single object. By doing so, you can hide the internal state of the object from the outside. This is known as information hiding.

    A class is an example of encapsulation. A class bundles data and methods into a single unit. And a class provides the access to its attributes via methods.

    The idea of information hiding is that if you have an attribute that isn’t visible to the outside, you can control the access to its value to make sure your object is always has a valid state.

- **Private Attributes**

    Private attributes can be only accessible from the methods of the class. In other words, they cannot be accessible from outside of the class.

    Python doesn’t have a concept of private attributes. In other words, all attributes are accessible from the outside of a class.

    By convention, you can define a private attribute by prefixing a single underscore (_):
    ```python
    _attribute
    ```
    If you prefix an attribute name with double underscores (__) like this:
    ```python
    __attribute
    ```
    Python will automatically change the name of the __attribute to:
    ```python
    _class__attribute
    ```
    ```python
    class Counter:
        def __init__(self):
            self.__current = 0

        def increment(self):
            self.__current += 1

        def value(self):
            return self.__current

        def reset(self):
            self.__current = 0
    ```
    ```python
    counter = Counter()
    print(counter.__current)
    ```
    Output:
    ```python
    AttributeError: 'Counter' object has no attribute '__current'
    ```
    However, you can access the __current attribute as _Counter___current like this:
    ```python
    counter = Counter()
    print(counter._Counter__current)
    ```



