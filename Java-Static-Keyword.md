## Static Keyword in Java

### Static Variables

**Concept:** Static variables, also known as class variables, are shared by all instances of the class.

**Detailed Example:**

```java
public class Counter {
    static int count = 0; // static variable

    Counter() {
        count++;
        System.out.println("Current count: " + count);
    }

    public static void main(String[] args) {
        Counter c1 = new Counter(); // Current count: 1
        Counter c2 = new Counter(); // Current count: 2
        Counter c3 = new Counter(); // Current count: 3
    }
} 
```


**Explanation:**

In this example, each time a `Counter` object is created, the static variable `count` is incremented. The `count` is shared across all instances, as demonstrated in the `main` method.

### Static Methods

**Concept:** Static methods belong to the class rather than any specific instance and can be called directly on the class.

**Detailed Example:**

```java
public class Calculator {
    static int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int result = Calculator.add(5, 10); // No object creation needed
        System.out.println("Sum: " + result); // Sum: 15
    }
}
```


**Explanation:**

Here, the `add` method is static and is called directly using `Calculator.add`, without needing to instantiate the `Calculator` class.

### Static Nested Classes

**Concept:** Static nested classes do not have access to the instance variables and methods of the outer class.

**Detailed Example:**

```java
public class OuterClass {
    private static String staticVar = "Static Variable";
    private String instanceVar = "Instance Variable";

    static class NestedClass {
        void display() {
            System.out.println("Accessing static variable: " + staticVar);
            // System.out.println("Accessing instance variable: " + instanceVar); // This would cause an error
        }
    }

    public static void main(String[] args) {
        OuterClass.NestedClass nested = new OuterClass.NestedClass();
        nested.display(); // Accessing static variable: Static Variable
    }
}
```

**Explanation:**

In this example, the `NestedClass` can access the static variable `staticVar` of `OuterClass`, but it cannot access the instance variable `instanceVar`. Attempting to do so would result in a compilation error.
