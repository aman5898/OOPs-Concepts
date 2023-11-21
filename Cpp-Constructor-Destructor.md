## C++ Version: Constructors

### Overview of Classes and Objects

- **Class:** Similar to Java, a class in C++ is a blueprint for creating objects.

- **Object:** An instance of a class.

### Introduction to Constructors

A constructor in C++ is a special member function used to initialize objects. It's called when an instance of a class is created.

### Example Class

- **Class Name:** Student

```cpp

class Student {
public:
    std::string name;
    int age;
    double psp;
};
```

## Creating an Object

To create an object of the Student class in C++:


```cpp

Student st; // Default constructor called
```
## Understanding Constructors

Like Java, C++ provides a default constructor if no constructor is explicitly defined.

### Default Constructor

C++ also creates a default constructor if none is provided.

It initializes members to default values: zero for fundamental types, and default constructors for class types.

### Example of Default Constructor

```cpp
class Student {
public:
    std::string name;
    int age;
    double psp;
    std::string univName;

    Student() : name(""), age(0), psp(0.0), univName("") {
        // This is a default constructor.
    }
};
```
## Manual Constructor

Creating a constructor manually in C++ offers control over object initialization.

### Example of a Manual Constructor


```cpp

class Student {
public:
    std::string name;
    int age = 21;
    std::string univName;
    double psp;

    // Manual constructor
    Student(const std::string& studentName, const std::string& universityName)
        : name(studentName), univName(universityName) {}
};
```

## Copy Constructor

C++ has a concept similar to Java's copy constructor, used to create a copy of an object.

### Example of a Copy Constructor

```cpp

class Student {
public:
    std::string name;
    int age;

    // Default constructor
    Student() : name(""), age(0) {}

    // Copy constructor
    Student(const Student& st) : name(st.name), age(st.age) {}
};
```
## Use Case of Copy Constructor

- Useful for creating deep copies of objects.
- Ensures each object has its own separate memory.
  
**Difference from Assignment:** In C++, `Student st2 = st1;` creates a shallow copy by default. A copy constructor creates a deep copy.

## Destructors in C++

### Concept of Destructors

A destructor is a special member function in C++ that is called automatically when an object goes out of scope or is explicitly deleted. The primary purpose of a destructor is to release resources that the object may have acquired during its lifetime. This includes deallocating memory, closing file handles, releasing network resources, etc. Destructors are especially important in a language like C++ where there is no garbage collection, and the programmer is responsible for managing memory and resources.

### Syntax and Characteristics

- The destructor has the same name as the class prefixed with a tilde `~`.
- It cannot have parameters and does not return anything, not even `void`.
- A class can have only one destructor.
- If a destructor is not defined by the programmer, the compiler provides a default destructor.

### Example of a Destructor

```cpp

class Resource {
public:
    Resource() {
        std::cout << "Resource acquired" << std::endl;
    }

    ~Resource() {
        std::cout << "Resource released" << std::endl;
    }
};

int main() {
    Resource res; // Constructor is called here
    // Destructor is called automatically when res goes out of scope
}
```

In this example, the Resource class acquires some resource in its constructor and releases it in its destructor. The destructor is called automatically when an object of Resource goes out of scope at the end of main().

## Destructors and Dynamic Memory

Destructors play a crucial role in classes that manage dynamic memory. This is a common pattern known as RAII (Resource Acquisition Is Initialization).

When a class allocates memory using new, it should release that memory in its destructor using delete.

### Example with Dynamic Memory

```cpp

class DynamicArray {
private:
    int* arr;
    int size;

public:
    DynamicArray(int s) : size(s) {
        arr = new int[size]; // Allocating memory
    }

    ~DynamicArray() {
        delete[] arr; // Releasing memory
    }
};

int main() {
    DynamicArray dArr(10); // Constructor allocates memory
    // Destructor releases memory when dArr goes out of scope
}
```
Here, DynamicArray allocates an array of integers in its constructor and deallocates it in its destructor.
