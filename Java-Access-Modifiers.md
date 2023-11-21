## Access Modifiers in Java

### Overview

Access modifiers in Java are keywords used before class, method, or variable declarations to control their accessibility from other parts of the program. The four types of access modifiers in Java are public, private, protected, and default (no modifier).

### Public Modifier

**Usage:** When a class, method, or variable is declared as public, it can be accessed from any other class.

**Example:**

```java
public class PublicExample {
    public void display() {
        System.out.println("Public Access Modifier Example");
    }
}
```

**Explanation:**

Here, both the class `PublicExample` and method `display` are accessible from any other class.

### Private Modifier

**Usage:** The private modifier restricts the access to the class members (variables and methods) within the class itself.

**Example:**

```java
public class PrivateExample {
    private int number;

    private void displayNumber() {
        System.out.println("Number: " + number);
    }
}
```

**Explanation:**

In this case, both `number` and `displayNumber` are not accessible outside the `PrivateExample` class.

### Protected Modifier

**Usage:** The protected access modifier allows access within the same package and subclasses.

**Detailed Example:**

```java
// In package 'packageOne'
public class Base {
    protected void display() {
        System.out.println("Protected Access Modifier Example");
    }
}

// In the same package or a different package with an import statement
public class Derived extends Base {
    public void testDisplay() {
        display(); // Accessible due to inheritance
    }
}
```

**Explanation:**

In this example, the `display` method is declared as protected in the `Base` class. It is accessible within the `Derived` class since `Derived` extends `Base`. This shows the use of the protected modifier in facilitating inheritance.

### Default Modifier (No Modifier)

**Usage:** When no access modifier is specified, it's known as default access. This allows access within the same package only.

**Example:**

```java
class DefaultExample {
    void display() {
        System.out.println("Default Access Modifier Example");
    }
}
```

**Explanation:**

Here, the `DefaultExample` class and `display` method are accessible within the same package.

### Key Points

- The choice of access modifier depends on the intended encapsulation level.
- Private members are typically used for internal class operations and data hiding.
- Public members form the class's interface with the outside world.
- Protected and default modifiers provide a controlled level of accessibility, especially useful in larger applications with multiple packages.

### Conclusion

Access modifiers are an essential aspect of Java, enabling encapsulation and security in code design. They play a crucial role in implementing the OOP principle of data hiding and abstraction.
