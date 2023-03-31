**What is map function?**
In Python, the "map" function is a built-in function that applies a given function to each item of an iterable (e.g., a list, tuple, or set), and returns an iterator that yields the results.

    map(function, iterable)

**What is reduce function?**
In Python, the "reduce" function is a built-in function that is used to apply a function to an iterable (e.g., a list, tuple, or set) and reduce it to a single value.

The "reduce" function takes two arguments: a function and an iterable. The function should take two arguments and return a single value, and the iterable should contain at least two values. The "reduce" function then applies the function to the first two values of the iterable, then to the result and the next value, and so on, until the entire iterable has been processed.
reduce(function, iterable)
from functools import reduce

    my_list = [1, 2, 3, 4, 5]

    def multiply(x, y):
        return x * y

    result = reduce(multiply, my_list)

    print(result) # prints: 120


**what is filter function?**
In Python, the "filter" function is a built-in function that is used to filter an iterable (e.g., a list, tuple, or set) based on a given function, and returns an iterator that yields the items for which the function returns "True".
filter(function, iterable)
my_list = [1, 2, 3, 4, 5]

    def is_even(x):
        return x % 2 == 0

    result = filter(is_even, my_list)

    print(list(result)) # prints: [2, 4]

**what is zip function?**
In Python, the "zip" function is a built-in function that is used to combine two or more iterables (e.g., lists, tuples, or sets) into a single iterable of tuples, where the i-th tuple contains the i-th element from each of the input iterables.

    zip(*iterables)

