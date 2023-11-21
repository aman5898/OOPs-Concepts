## Definition and Concept
Similar to Java, a C++ class is a blueprint for objects. It encapsulates data and functions. Objects in C++ are instances of a class. Memory management is more explicit in C++.

## Creating a Class
Use the `class` keyword, similar to Java.


```cpp
class Car {
    // Fields (private by default)
    std::string brand;
    int year;

public:
    // Constructor
    Car(std::string brand, int year);

    // Destructor
    ~Car();

    // Method
    void displayInfo();
};

// Car.cpp
#include <iostream>

Car::Car(std::string b, int y) : brand(b), year(y) {}

Car::~Car() {
    // Cleanup code (if necessary)
}

void Car::displayInfo() {
    std::cout << "Car Brand: " << brand << ", Year: " << year << std::endl;
}
```

## Creating an Object

Objects can be created on the stack or the heap (using pointers).

### Stack:
```cpp
Car myCar("Toyota", 2021);
```

### Heap
```cpp
Car* myCar = new Car("Toyota", 2021);
```


```cpp

// Main.cpp

int main() {
    // Creating an object on the stack
    Car myCar("Toyota", 2021);

    // Calling method on the object
    myCar.displayInfo();

    // For heap allocation (remember to delete)
    // Car* myCarPtr = new Car("Toyota", 2021);
    // myCarPtr->displayInfo();
    // delete myCarPtr;

    return 0;
}
```
## Additional C++ Features:

- **Operator Overloading:** You can define custom behavior for operators in C++.

- **Templates:** C++ supports generic programming through templates.

- **Multiple Inheritance:** C++ allows a class to inherit from multiple classes.

