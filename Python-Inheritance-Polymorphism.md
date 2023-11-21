## Inheritance in Python

### Concept of Inheritance

- Inheritance in Python, as in other Object-Oriented Programming (OOP) languages, allows for the creation of a hierarchy between classes. This concept facilitates the reuse of code and the establishment of relationships that mirror real-world categorizations.

### Understanding Inheritance through Hierarchy

- **Parent-Child Relationship:** Just like in Java, inheritance in Python is about a parent-child relationship between classes, where the child class inherits attributes and methods from the parent class.

### Example of Inheritance

```python

class Animal:
    def walk(self):
        print("Animal walks")

class Dog(Animal):
    def bark(self):
        print("Dog barks")
```
## In this example, Dog inherits from Animal, so a Dog instance can both walk and bark. The walk method is inherited from the Animal class.

### Parent-Child Relationship in Code

- **The Inheritance Syntax:** In Python, inheritance is established by listing the parent class in parentheses after the child class's name.

### Example of Parent-Child Code Relationship


```python

class User:
    def __init__(self, userName):
        self.userName = userName

    def login(self):
        # login code
        pass

class Instructor(User):
    def __init__(self, userName, batchName, avgRating):
        super().__init__(userName)
        self.batchName = batchName
        self.avgRating = avgRating

    def schedule_class(self):
        # schedule class code
        pass
```

In this example, Instructor extends User, inheriting the userName attribute and login method.

### Constructor Chaining in Inheritance

- **Constructor Chaining:** Similar to Java, constructor chaining in Python refers to a child class constructor calling its parent class's constructor.

### Example of Constructor Chaining


```python

class A:
    def __init__(self):
        print("Constructor of A")

class B(A):
    def __init__(self):
        super().__init__()
        print("Constructor of B")

class C(B):
    def __init__(self):
        super().__init__()
        print("Constructor of C")

# Creating an instance of C
c = C()  # This will print constructors of A, B, and C in order.
```

## Using super in Constructors

- **The super Function:** Python uses `super()` to call methods from the parent class.

### Example Using super


```python

class C(B):
    def __init__(self, message):
        super().__init__()  # Calls constructor of B
        print(f"Constructor of C with message: {message}")
```

## Abstraction in Inheritance

- **Abstraction:** Python supports abstraction in inheritance, allowing generic parent classes to define a common interface which specialized child classes can implement or extend.

## Conclusion

In Python, inheritance works similarly to Java but with some syntactic differences. Python uses `super()` for constructor chaining and method overriding, and it defines child classes with a more straightforward syntax. Like Java, Python's inheritance supports code reuse and abstraction, making it a fundamental feature in object-oriented design.
