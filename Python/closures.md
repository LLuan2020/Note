**What is closure?**

In Python, you can define a function from the inside of another function. And this function is called a nested function. For example:
```python
def say():
    greeting = 'Hello'

    def display():
        print(greeting)

    display()
```
In this example, we define the display function inside the say function. The display function is called a nested function.

Inside the display function, you access the greeting variable from its nonlocal scope.

Python calls the greeting variable a free variable.

When you look at the display function, you actually look at:

- The display function itself.
- And the free variable greeting with the value 'Hello'.
So the combination of the display function and greeting variable is called a closure:

![My Remote Image](https://www.pythontutorial.net/wp-content/uploads/2020/11/Python-Closure-Example.png)

**By definition, a closure is a nested function that references one or more variables from its enclosing scope.**

- **Returning an inner function**

In Python, a function can return a value which is another function. For example:
```python
def say():
    greeting = 'Hello'

    def display():
        print(greeting)

    return display    
```
In this example, the say function returns the display function instead of executing it.

Also, when the say function returns the display function, it actually returns a closure:

![My Remote Image](https://www.pythontutorial.net/wp-content/uploads/2020/11/Python-Closures.png)

The following assigns the return value of the say function to a variable fn. Since fn is a function, you can execute it:
```python
fn = say()
fn()
```
Output:

Hello

The say function executes and returns a function. When the fn function executes, the say function already completes.

In other words, the scope of the say function was gone at the time the fn function executes.

Since the greeting variable belongs to the scope of the say function, it should also be destroyed with the scope of the function.

However, you still see that fn displays the value of the message variable.

- **When Python creates the closure**

Python creates a new scope when a function executes. If that function creates a closure, Python also creates a new closure as well. Consider the following example:

**First**, define a function called multiplier that returns a closure:
```python
def multiplier(x):
    def multiply(y):
        return x * y
    return multiply
```

The multiplier function returns the multiplication of two arguments. However, it uses a closure instead.

**Second**, call the multiplier function three times:
```python
m1 = multiplier(1)
m2 = multiplier(2)
m3 = multiplier(3)
```
These function calls create three closures. Each function multiplies a number with 1, 2, and 3.

**Third**, execute functions of the closures:
```python
print(m1(10))
print(m2(10))
print(m3(10))
```
Output:

10
20
30
