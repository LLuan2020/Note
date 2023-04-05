## Lambda Function
**What are lambda functions in Python, and how are they used?**

It is created using the "lambda" keyword, which is followed by a comma-separated list of arguments, a colon, and a single expression that is evaluated and returned when the function is called.
```python
sum = lambda x, y: x + y
result = sum(5, 10)
print(result)  # 15
```
In this example, the lambda function takes two arguments ("x" and "y"), adds them together, and returns the result. The lambda function is assigned to the variable "sum", which can be used to call the function with different arguments.
```python
numbers = [1, 2, 3, 4, 5]
squares = list(map(lambda x: x**2, numbers))
print(squares)  # [1, 4, 9, 16, 25]
```
In this example, the lambda function takes a single argument ("x"), squares it, and returns the result. The "map" function is used to apply the lambda function to each element of the "numbers" list, and the resulting values are collected into a new list called "squares".
