## *args VS **kwargs?

- **What is \*args?**
    
    args is used to pass a variable number of non-keyword arguments to a function. The asterisk () before the parameter name "args" indicates that the function can accept any number of arguments, which are then passed as a tuple to the function. 
    ```python
    def my_func(*args):
        for arg in args:
            print(arg)

    my_func(1, 2, 3, "hello") # prints: 1 2 3 hello
    ```
    - Python *args argument exhausts positional arguments
    
    If you use the *args argument, you cannot add more positional arguments. However, you can use keyword arguments.

    The following example results in an error because it uses a positional argument after the *arg argument:
    ```python
    def add(x, y, *args, z):
        return x + y + sum(args) + z

    add(10, 20, 30, 40, 50)
    ```
    Error:
    ```python
    TypeError: add() missing 1 required keyword-only argument: 'z'
    ```
    To fix it, you need to use a keyword argument after the *args argument as follows:
    ```python
    def add(x, y, *args, z):
        return x + y + sum(args) + z

    add(10, 20, 30, 40, z=50)
    ```
    In this example, Python assigns 10 to x, 20 to y,(30,40) to args, and 50 to z.
    - Unpacking arguments

    The following point function accepts two arguments and returns a string representation of a point with x-coordinate and y-coordinate:
    ```python
    def point(x, y):
        return f'({x},{y})'
    ```
    If you pass a tuple to the point function, you’ll get an error:
    ```python
    a = (0, 0)
    origin = point(a)
    ```
    Error:
    ```python
    TypeError: point() missing 1 required positional argument: 'y'
    ```
    To fix this, you need to prefix the tuple a with the operator * like this:
    ```python
    def point(x, y):
        return f'({x},{y})'
    a = (0, 0)
    origin = point(*a)
    print(origin)
    ```
    Output:
    ```python
    (0,0)
    ```
    When you precede the argument a with the operator *, Python unpacks the tuple and assigns its elements to x and y parameters.

- **What is \*\*kwargs?**

    kwargs is used to pass a variable number of keyword arguments (or named arguments) to a function. The double asterisk () before the parameter name "kwargs" indicates that the function can accept any number of keyword arguments, which are then passed as a dictionary to the function.
    ```python
    def my_func(**kwargs):
        for key, value in kwargs.items():
            print(key, value)

    my_func(name="John", age=30, city="New York") # prints: name John, age 30, city New York.

    def connect(**kwargs):
    print(kwargs)

    config = {'server': 'localhost',
            'port': 3306,
            'user': 'root',
            'password': 'Py1thon!Xt12'}

    connect(**config)
    ```
    Using *args and \*\*kwargs can be useful when you don't know how many arguments a function will need to accept, or when you want to allow the user to pass a variable number of arguments to a function in a flexible way.



