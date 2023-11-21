## Classes and Objects in Java

### Definition and Concept

In Java, a class is a blueprint for creating objects. It defines a data type by bundling data and methods that operate on the data into a single unit. An object is an instance of a class, encapsulating data and behavior specific to that type.

### Creating a Class

A class in Java is defined using the `class` keyword. For example, consider a class `Car`:

```java
public class Car {
    // Fields (or attributes)
    String brand;
    int year;

    // Constructor
    public Car(String brand, int year) {
        this.brand = brand;
        this.year = year;
    }

    // Methods
    public void displayInfo() {
        System.out.println("Car Brand: " + brand + ", Year: " + year);
    }
}
```

**Explanation:**

In this example, the `Car` class has two fields: `brand` and `year`. It also has a constructor to initialize these fields and a method `displayInfo` to display the car's information.

### Creating an Object

An object is created (instantiated) using the `new` keyword:

```java
public class Main {
    public static void main(String[] args) {
        // Creating an object of Car
        Car myCar = new Car("Toyota", 2021);

        // Calling method on the object
        myCar.displayInfo();
    }
}
```

**Explanation:**

In the `Main` class, we create an instance of `Car` named `myCar` and call the `displayInfo` method on it. This will output the car's brand and year.
