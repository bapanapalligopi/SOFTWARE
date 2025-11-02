**Factory Design Pattern**

### **Factory Pattern**

The **Factory Pattern** is a **creational design pattern** that provides an interface for creating objects but allows subclasses to alter the type of objects that will be created.

In simpler terms, instead of calling constructors directly to create an object, we use a **factory method** to create it based on some input or logic.

---

### **When Should You Use It?**

Use the Factory Pattern when:

* The client code needs to work with multiple object types.
* The type of object to instantiate must be decided at runtime.
* Object creation logic is complex or should be hidden.

---

### **Real-World Analogy: Ordering Pizza**

You walk into a pizza shop and say, “I’d like a pizza.”
The shop asks, “Which type — Margherita, Pepperoni, or Veggie?”
Based on your answer, the kitchen prepares that pizza and hands it to you.

You (the client) don’t know or care about the exact cooking process — you just get the pizza you requested.
Similarly, the **Factory Pattern** hides the creation logic and gives you the right object based on your request.

---

### **Basic Structure of the Factory Pattern**

**Components:**

1. **Product (Interface or Abstract Class)** – Defines common behavior.
2. **Concrete Products** – Implementations of the product interface.
3. **Factory** – A class that decides which product to instantiate.

---

### **Example – Java Implementation**

#### **Without Factory (Bad Practice)**

```java
class LogisticsService {
    void send(String type) {
        if (type.equalsIgnoreCase("Air")) {
            AirTransport air = new AirTransport();
            air.deliver();
        } else if (type.equalsIgnoreCase("Road")) {
            RoadTransport road = new RoadTransport();
            road.deliver();
        }
    }
}

class AirTransport {
    void deliver() {
        System.out.println("Delivery by Air");
    }
}

class RoadTransport {
    void deliver() {
        System.out.println("Delivery by Road");
    }
}
```

**Issues:**

* Violates **Open/Closed Principle** — new modes (like Ship) require modifying existing code.
* Tight coupling between `LogisticsService` and transport classes.
* Hard to maintain or test.

---

#### **With Factory (Good Practice)**

```java
// Product Interface
interface Transport {
    void deliver();
}

// Concrete Products
class AirTransport implements Transport {
    public void deliver() {
        System.out.println("Delivery by Air");
    }
}

class RoadTransport implements Transport {
    public void deliver() {
        System.out.println("Delivery by Road");
    }
}

// Factory Class
class TransportFactory {
    public static Transport getTransport(String type) {
        if (type.equalsIgnoreCase("Air")) {
            return new AirTransport();
        } else if (type.equalsIgnoreCase("Road")) {
            return new RoadTransport();
        }
        throw new IllegalArgumentException("Unknown transport type");
    }
}

// Client Code
public class LogisticsService {
    public static void main(String[] args) {
        Transport transport = TransportFactory.getTransport("Air");
        transport.deliver();
    }
}
```

---

### **Understanding the Improvement**

✅ The `TransportFactory` handles object creation.
✅ `LogisticsService` focuses only on the business logic.
✅ Adding new transport types (like `ShipTransport`) requires **no change** to existing classes — just extend the factory.

---

### **Benefits**

* **Loose Coupling**: The client does not depend on concrete classes.
* **Extensible**: New types can be added easily (Open/Closed Principle).
* **Centralized Object Creation**: Clear separation of concerns.
* **Better Maintainability and Testing**.

---

### **Drawbacks**

* Adds extra code (factory classes/interfaces).
* May be overkill for simple programs.

---

### **UML Class Diagram**

```
         +------------------+
         |    Transport     |  <---- Interface / Abstract Class
         +------------------+
         | + deliver()      |
         +------------------+
               /   \
              /     \
 +------------------+    +------------------+
 |  AirTransport    |    |  RoadTransport   |
 +------------------+    +------------------+
 | + deliver()      |    | + deliver()      |
 +------------------+    +------------------+
              ↑
              |
    +----------------------+
    |   TransportFactory   |
    +----------------------+
    | + getTransport()     |
    +----------------------+
              ↑
              |
    +----------------------+
    |  LogisticsService    |
    +----------------------+
    | + main()             |
    +----------------------+
```

---

### **Conclusion**

The **Factory Pattern** is one of the most commonly used creational patterns in real-world software.
It promotes **loose coupling**, **reusability**, and **maintainability** — making it perfect for systems that evolve over time or handle multiple similar object types.
