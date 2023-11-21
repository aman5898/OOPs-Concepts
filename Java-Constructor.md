## Constructors in Java

### Overview of Classes and Objects

- **Class:** A blueprint for an object that defines its properties and behaviors.

- **Object:** An instance of a class.

### Introduction to Constructors

A constructor in Java is a special method used to initialize objects. It is called when an instance of a class is created.

### Example Class

- **Class Name:** Student

```java

public class Student {
    String name;
    int age;
    double psp;
}
```
## Creating an Object

To create an object of the Student class, we use:


```java

Student st = new Student();
```
## Understanding Constructors

- The `Student` in `new Student()` is the constructor.
- If no constructor is explicitly defined, Java provides a default constructor.

### Default Constructor

- Automatically created if no constructor is defined.
- Initializes each attribute to its default value: 0 for integers, null for objects, 0.0 for doubles, etc.
- Only assigns default values if attributes are not already initialized.

### Example of Default Constructor

```java

class Student {
    String name;
    int age;
    double psp;
    String univName;

    Student() {
        // This is a default constructor.
        name = null;
        age = 0;
        psp = 0.0;
        univName = null;
    }
}
```
**Note:** Writing the default constructor explicitly is not necessary as it is automatically generated.

### When is a Default Constructor Not Created?

A default constructor is not created if a class has any other constructor defined.

### Characteristics of a Constructor

- Same name as the class.
- No return type, not even void.
- Can be public, private, protected, or package-private (no modifier).

## Manual Constructor

Creating a constructor manually allows for more control and customization when creating objects.

### Example of a Manual Constructor

```java

public class Student {
    String name;
    private int age = 21;
    String univName;
    double psp;

    // Manual constructor
    public Student(String studentName, String universityName) {
        name = studentName;
        univName = universityName;
    }
}
```
### Usage:

```java

public class Client {
    public static void main(String[] args) {
        Student st = new Student("Utkarsh", "JIIT");
    }
}
```
## Copy Constructor

A copy constructor creates a new object as a copy of an existing object.

### Example of a Copy Constructor

```java

class Student {
    String name;
    int age;

    // Default constructor
    Student() {
        name = null;
        age = 0;
    }

    // Copy constructor
    Student(Student st) {
        name = st.name;
        age = st.age;
    }
}
```
### Usage:

```java

Student st1 = new Student();
st1.name = "Utkarsh";
st1.age = 27;

Student st2 = new Student(st1); // Using the copy constructor
```

## Use Case of Copy Constructor

- Useful for creating a new object with the same data as an existing object.
- Allows copying of private attributes that might not be accessible otherwise.

**Difference from Assignment:** `Student st2 = st1;` only points `st2` to the same object as `st1`. A copy constructor creates a separate object with its own memory space.

