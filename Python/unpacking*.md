## Unpacking *

- Extended unpacking using the * operator
    Sometimes, you don’t want to unpack every single item in a tuple. For example, you may want to unpack the first and second elements. In this case, you can use the * operator. For example:

    ```python
    r, g, *other = (192, 210, 100, 0.5)
    192
    210
    [100, 0.5]
    ```

- Using the * operator on the right hand side
    Python allows you to use the * operator on the right-hand side. Suppose that you have two tuples:
    ```python
    odd_numbers = (1, 3, 5)
    even_numbers = (2, 4, 6)
    ```
    The following example uses the * operator to unpack those tuples and merge them into a single tuple:
    ```python
    numbers = (*odd_numbers, *even_numbers)
    print(numbers)
    ```
    Output:
    ```python
    (1, 3, 5, 2, 4, 6)
    ```