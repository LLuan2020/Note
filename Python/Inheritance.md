## What is inheritance?

Inheritance is when an object or class is based on another object or class and uses the same implementation. For example, you could have both a Car and a Motorcycle class that inherits from a Vehicle class.

Inheritance allows a class to reuse the logic of an existing class.

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        return f"Hi, it's {self.name}"

class Employee(Person):
    def __init__(self, name, job_title):
        self.name = name
        self.job_title = job_title

>>>employee = Employee('John', 'Python Developer')
>>>print(employee.greet())

Hi, it's John
```
To reuse the greet() method from the Person class in the Employee class, you can create a relationship between the Person and Employee classes. To do it, you use inheritance so that the Employee class inherits from the Person class.

By doing this, the Employee class behaves the same as the Person class without redefining the greet() method.

This is a single inheritance because the Employee inherits from a single class (Person). Note that Python also supports multiple inheritances where a class inherits from multiple classes.
