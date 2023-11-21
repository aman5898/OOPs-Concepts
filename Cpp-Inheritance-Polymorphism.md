C++ Version: Inheritance
Concept of Inheritance
Inheritance in C++ is similar to Java, allowing the creation of a class hierarchy.
It enables a derived (child) class to inherit attributes and behaviors from a base (parent) class.
Understanding Inheritance through Hierarchy
A derived class can inherit methods and fields from a base class, except those marked as private.
Example of Inheritance
cpp

class Animal {
public:
    void walk() {
        std::cout << "Animal walks" << std::endl;
    }
};

class Dog : public Animal {
public:
    void bark() {
        std::cout << "Dog barks" << std::endl;
    }
};
Here, Dog extends Animal, inheriting the walk method.
Parent-Child Relationship in Code
The inheritance relationship is established using : followed by the access specifier (public, protected, or private).
Example of Parent-Child Code Relationship
cpp

class User {
public:
    std::string userName;
    void login() {
        // login code
    }
};

class Instructor : public User {
public:
    std::string batchName;
    double avgRating;
    void scheduleClass() {
        // schedule class code
    }
};
Instructor extends User, inheriting userName and login().
Constructor Chaining in Inheritance
Like Java, C++ also has constructor chaining, where the base class constructor is called before the derived class constructor.
Example of Constructor Chaining
cpp

class A {
public:
    A() {
        std::cout << "Constructor of A" << std::endl;
    }
};

class B : public A {
public:
    B() {
        std::cout << "Constructor of B" << std::endl;
    }
};

class C : public B {
public:
    C() {
        std::cout << "Constructor of C" << std::endl;
    }
};

int main() {
    C c; // This will print constructors of A, B, and C in order.
}
Using super in Constructors
In C++, the equivalent of Java's super is the base class constructor call. It's used with the base class name and parentheses.
Example Using Base Class Constructor
cpp

class C : public B {
public:
    C(std::string message) : B() {
        std::cout << "Constructor of C with message: " + message << std::endl;
    }
};
The B() constructor is explicitly called from C's constructor.
Abstraction in Inheritance
Like Java, C++ uses inheritance to support abstraction.
Abstract classes in C++ are created using pure virtual functions.

Inheritance in C++: Extended Concepts and Features
Access Control in Inheritance
C++ provides more control over inheritance through three types of access: public, protected, and private.
public inheritance: The most common form, where public and protected members of the base class remain public and protected in the derived class.
protected inheritance: Public and protected members of the base class become protected in the derived class.
private inheritance: Public and protected members of the base class become private in the derived class.
Multiple Inheritance
Unlike Java, C++ supports multiple inheritance, where a class can inherit from more than one base class.
This feature can be powerful but also introduces complexity, such as the "diamond problem".
Example of Multiple Inheritance
cpp

class Base1 {
public:
    void function1() {}
};

class Base2 {
public:
    void function2() {}
};

class Derived : public Base1, public Base2 {
    // Inherits function1 from Base1 and function2 from Base2
};
Virtual Functions and Polymorphism
C++ uses virtual functions to enable polymorphism, a core concept in OOP.
A virtual function in a base class can be overridden in a derived class to provide specific behavior.
Virtual functions are crucial for achieving runtime polymorphism.
Example of Virtual Functions
cpp

class Base {
public:
    virtual void show() {
        std::cout << "Base class show" << std::endl;
    }
};

class Derived : public Base {
public:
    void show() override {
        std::cout << "Derived class show" << std::endl;
    }
};
Abstract Classes and Pure Virtual Functions
An abstract class in C++ is a class that has at least one pure virtual function.
Pure virtual functions are declared by assigning 0 to them, and they must be overridden in derived classes.
Example of an Abstract Class
cpp

class AbstractBase {
public:
    virtual void pureVirtualFunction() = 0; // Pure virtual function
};

class ConcreteClass : public AbstractBase {
public:
    void pureVirtualFunction() override {
        // implementation
    }
};
The Diamond Problem and Virtual Inheritance
The diamond problem occurs in multiple inheritance when two classes B and C inherit from A, and class D inherits from both B and C.
This creates ambiguity regarding which A class members D should inherit.
C++ resolves this using virtual inheritance.
Example of Virtual Inheritance
cpp

class A {
public:
    void functionA() {}
};

class B : virtual public A {};

class C : virtual public A {};

class D : public B, public C {
    // D now has a single copy of A's members
};
Constructor and Destructor Call Order
In C++, the constructors of base classes are called in the order of inheritance, and destructors are called in the reverse order.
Understanding this order is crucial for proper resource management in more complex class hierarchies.