## Static Variables

- Python doesn't have a direct equivalent to Java's static variables. However, class variables in Python share some similarities.

### Concept

- Class variables in Python are shared across all instances of the class.

### Detailed Example:


```python

class Counter:
    count = 0  # Class variable

    def __init__(self):
        Counter.count += 1
        print(f"Current count: {Counter.count}")

# Creating instances
c1 = Counter() # Current count: 1
c2 = Counter() # Current count: 2
c3 = Counter() # Current count: 3
```
### Explanation

- Each time a `Counter` object is created, the class variable `count` is incremented. This variable is shared across all instances.

### Static Methods

- Python supports static methods using the `@staticmethod` decorator.

### Concept

- Static methods in Python do not receive an implicit first argument and can be called on a class without creating an instance.

### Detailed Example:


```python

class Calculator:
    @staticmethod
    def add(a, b):
        return a + b

# Calling static method
result = Calculator.add(5, 10)  # No instance is created
print(f"Sum: {result}")  # Sum: 15
```

### Explanation

- The `add` method is a static method and is called directly on the `Calculator` class without needing to instantiate it.

### Static Nested Classes

- Python doesn't have an exact equivalent to Java's static nested classes. However, nested classes in Python can access variables of the enclosing class.

### Detailed Example:


```python

class OuterClass:
    staticVar = "Static Variable"

    class NestedClass:
        def display(self):
            print(f"Accessing static variable: {OuterClass.staticVar}")

# Using the nested class
nested = OuterClass.NestedClass()
nested.display()  # Accessing static variable: Static Variable
```

### Explanation

- The `NestedClass` can access the class variable `staticVar` of `OuterClass`. In Python, nested classes behave similarly to static nested classes in Java, but they can also access non-static variables if provided with an instance of the outer class.

## Conclusion

While Python does not have the `static` keyword like Java, it provides similar functionalities through class variables, static methods (using `@staticmethod`), and nested classes. These features allow Python to handle shared data and methods at the class level, offering a different but comparable approach to Java's static concept.
