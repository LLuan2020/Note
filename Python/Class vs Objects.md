**What is a class?**

A class is a prototype that consists of objects in different states and with different behaviors. It has a number of methods that are common the objects present within that class.
    class Person:
        pass
To create an instance of a class, you use the class name with parentheses like this:
    person = Person()

**What is class variable?**

Class variables are bound to the class. They’re shared by all instances of that class.

    class HtmlDocument:
        extension = 'html'
        version = '5'
Both extension and version are the class variables of the HtmlDocument class. They’re bound to the HtmlDocument class.

    print(HtmlDocument.extension) # html
    print(HtmlDocument.version) # 5

Python stores class variables in the __dict__ attribute. The __dict__ is a mapping proxy, which is a dictionary. For example:
from pprint import pprint

    class HtmlDocument:
        extension = 'html'
        version = '5'

    HtmlDocument.media_type = 'text/html'
    pprint(HtmlDocument.__dict__)

Output:
    mappingproxy({'__dict__': <attribute '__dict__' of 'HtmlDocument' objects>,
                '__doc__': None,
                '__module__': '__main__',
                '__weakref__': <attribute '__weakref__' of 'HtmlDocument' objects>,
                'extension': 'html',
                'media_type': 'text/html',
                'version': '5'})

Use dot notation or getattr() function to get the value of a class attribute.
Use dot notation or setattr() function to set the value of a class attribute.
    setattr(HtmlDocument, media_type, 'text/html')
    print(HtmlDocument.media_type)

**What is the purpose of the "self" keyword in Python classes?**

In Python, the "self" keyword is used to refer to the instance of a class within its own methods. It is a convention used to make the code more readable and to differentiate between instance variables and local variables.

When we define a method within a class, we include the "self" parameter as the first parameter. This parameter refers to the instance of the class that the method is being called on, and allows us to access the instance variables and methods within the class.

    class Request:
        def send(*args):
            print('Sent', args)

The following calls the send function from the Request class:   

    Request.send()    

Output:
    
    Sent ()

    http_request.send()

Output:
    
    Sent (<__main__.Request object at 0x000001374AF4D580>,)

**What is the difference between a class and a structure?**

Class: User-defined blueprint from which objects are created. It consists of methods or set of instructions that are to be performed on the objects.
Structure: A structure is basically a user-defined collection of variables which are of different data types.

**What is an object?**

An object is a real-world entity which is the basic unit of OOPs for example chair, cat, dog, etc. Different objects have different states or attributes, and behaviors.

**What is \_\_init__() method?**

When you create a new object of a class, Python automatically calls the __init__() method to initialize the object’s attributes. We can use the __init__() method to initialize the object’s attributes.

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age


if __name__ == '__main__':
    person = Person('John', 25)
    print(f"I'm {person.name}. I'm {person.age} years old.")

When you create an instance of the Person class, Python performs two things:

- First, create a new instance of the Person class by setting the object’s namespace such as __dict__ attribute to empty ({}).
- Second, call the __init__ method to initialize the attributes of the newly created object.