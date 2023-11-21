## Inheritance in Java

### Concept of Inheritance

Inheritance in Object-Oriented Programming (OOP) allows for creating a hierarchy or relationship between classes, mirroring the way humans categorize and understand real-world entities.

### Understanding Inheritance through Hierarchy

- Inheritance represents a parent-child relationship between classes.
- It allows a child class to inherit properties and behaviors (methods and fields) from a parent class.

### Example of Inheritance

```java

class Animal {
    void walk() {
        System.out.println("Animal walks");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```
In this example, `Dog` extends `Animal`. So, a `Dog` can both walk and bark. The ability to walk is inherited from the `Animal` class.

### Parent-Child Relationship in Code

- The `extends` keyword in Java is used to establish an inheritance relationship.
- The child class inherits all non-private members of the parent class.

### Example of Parent-Child Code Relationship

```java

class User {
    String userName;
    
    void login() {
        // login code
    }
}

class Instructor extends User {
    String batchName;
    double avgRating;
    
    void scheduleClass() {
        // schedule class code
    }
}
```
In this example, `Instructor` extends `User`, inheriting the `userName` and `login()` method.

## Constructor Chaining in Inheritance

Constructor chaining refers to the process where a child class constructor calls the constructor of its parent class.

### How Constructor Chaining Works

- When an object of a child class is created, the constructor of the parent class is called first.
- If the child class does not explicitly call a super constructor, the default constructor of the parent class is invoked.

### Example of Constructor Chaining

```java

class A {
    A() {
        System.out.println("Constructor of A");
    }
}

class B extends A {
    B() {
        System.out.println("Constructor of B");
    }
}

class C extends B {
    C() {
        System.out.println("Constructor of C");
    }
}

public class Test {
    public static void main(String[] args) {
        C c = new C(); // This will print constructors of A, B, and C in order.
    }
}
```
## Using `super` in Constructors

- The `super` keyword is used to explicitly call a parent class constructor.
- It must be the first statement in the child class constructor.

### Example Using `super`

```java

class C extends B {
    C(String message) {
        super(); // Calls constructor of B
        System.out.println("Constructor of C with message: " + message);
    }
}
```
## Abstraction in Inheritance

Inheritance supports the concept of abstraction, allowing more generic (parent) classes to define a common interface or behavior, which specialized (child) classes can implement or extend.

