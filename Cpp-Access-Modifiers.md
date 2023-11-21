C++ Access Modifiers

Overview
C++ also uses access modifiers to control access to class members (methods and variables).
The three primary access modifiers in C++ are public, private, and protected.
There is no direct equivalent to Java's default (package-private) access in C++, but similar behavior can be achieved using specific patterns.
Public Modifier
Similar to Java, public members in C++ are accessible from anywhere the object is visible.
```cpp
Copy code
class PublicExample {
public:
    void display() {
        std::cout << "Public Access Modifier Example" << std::endl;
    }
};
```
Here, the display method is accessible from any part of the program.
Private Modifier
In C++, private members are accessible only within the same class.
```cpp
Copy code
class PrivateExample {
private:
    int number;

    void displayNumber() {
        std::cout << "Number: " << number << std::endl;
    }
};
```

Similar to Java, number and displayNumber are not accessible outside PrivateExample.
Protected Modifier
Protected in C++ is similar to Java. It allows access within the same class, derived classes, but not from outside classes.
```cpp
Copy code
class Base {
protected:
    void display() {
        std::cout << "Protected Access Modifier Example" << std::endl;
    }
};

class Derived : public Base {
public:
    void testDisplay() {
        display(); // Accessible due to inheritance
    }
};
```

display is accessible in Derived due to inheritance.
Default Access (No Modifier)
In C++, when no access modifier is specified, the default is private for classes and public for structs.
To mimic Java's package-private access, you'd typically use private or protected and organize your code with careful use of friend classes or functions.

```cpp
Copy code
class DefaultExample {
    void display() {
        std::cout << "Default Access Modifier Example" << std::endl;
    }
};
```

display is accessible only within DefaultExample.
Key Points
C++ does not have a direct equivalent to Java's default (package-private) access.
The choice of access modifier in C++ is crucial for encapsulation and controlling the scope of class members.
Understanding how and when to use each modifier is key to effective C++ class design.
