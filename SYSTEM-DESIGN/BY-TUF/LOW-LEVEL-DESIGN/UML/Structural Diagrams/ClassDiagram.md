# UML Class Diagram Overview

## **Introduction**

A **UML Class Diagram** provides a high-level overview of the system architecture. It captures the system's **classes, interfaces, enumerations**, their **attributes and operations (methods)**, and the **relationships** among them.

It is instrumental in both forward and reverse engineering processes and is widely used in modeling object-oriented systems.

Class diagrams support various design activities including **domain modeling, data modeling**, and the **architectural representation** of systems. These diagrams are often created during the early stages of the software development lifecycle and refined as the project progresses.

Looking at a class diagram, you must quickly be able to understand the system's structure and how different components interact with each other. This is particularly useful for new team members or stakeholders who need to get up to speed with the system's design regardless of understanding the underlying code.

In this section, we will explore the various components of UML Class Diagrams, including **classes, attributes, methods, and relationships**. We will also discuss the **notations** used to represent these elements and how they can be effectively utilized in software design.

---

## **UML Class Notations**

### **1. Class Representation**

A class in UML is depicted as a **rectangle divided into three compartments**:

* **Top compartment:** Contains the class name (bold and centered).
* **Middle compartment:** Lists the attributes.
* **Bottom compartment:** Lists the operations (methods).

Each attribute or method is listed with its **visibility marker**, **name**, and **type** (for attributes) or **return type** (for methods). Parameters for methods are also specified in parentheses.

---

### **2. Visibility Markers**

Visibility markers define access levels for attributes and operations:

* **Public (+):** Accessible from any other class.
* **Private (-):** Accessible only within the class itself.
* **Protected (#):** Accessible within the class and its subclasses.
* **Package (~):** Accessible within the same package.

These markers help enforce **encapsulation**, a core principle in object-oriented design.

---

### **3. Attributes and Method System**

#### **Attributes Syntax**

`visibility name: Type [multiplicity] = DefaultValue`

**Breakdown:**

* `visibility`: The visibility marker (e.g., +, -, #, ~).
* `name`: The name of the attribute.
* `Type`: The data type of the attribute (e.g., int, String).
* `multiplicity`: Optional, indicates how many instances can exist (e.g., 0..1, 1..*).
* `DefaultValue`: Optional, specifies a default value.

**Example:**
Java → `public int age = 21;`
UML → `+ age: int = 21`

---

#### **Methods Syntax**

`visibility name(parameterName1: Type1,...): ReturnType`

**Breakdown:**

* `visibility`: The visibility marker (e.g., +, -, #, ~).
* `name`: The name of the method.
* `parameterName`: The name of the parameter.
* `Type`: The data type of the parameter.
* `ReturnType`: The return type of the method.

**Example:**
Java →

```java
private boolean isAdult(int age) { return age >= 18; }
```

UML → `- isAdult(age: int): boolean`

Optional elements like **multiplicity**, **default values**, and **stereotypes** (e.g., `<<constructor>>`, `<<static>>`) can also be included to enrich the diagram.

---

### **4. Interface**

An **interface** defines a contract that other classes must follow. It contains only abstract methods (no implementation).

UML interface representation includes:

* **Name compartment:** With stereotype `<<interface>>` and interface name.
* **Operation compartment:** With method signatures.

Interfaces may optionally have an **attribute compartment** for constants.

---

### **5. Abstract Class**

An **abstract class** cannot be instantiated and may contain both implemented and unimplemented (abstract) methods.
It is represented in UML with the `<<abstract>>` stereotype above the class name, and the class name is italicized.

---

### **6. Enumeration (Enum)**

An **enumeration** defines a fixed set of named values (literals).
It is represented with the stereotype `<<enumeration>>`, where literals are listed in a separate compartment.

---

## **Perspectives of Class Diagrams**

### **1. Conceptual Perspective**

* Focus: High-level system concepts and their relationships.
* Audience: Business analysts and domain experts.
* Style:

  * Classes represent real-world entities (e.g., `Customer`, `Order`, `Invoice`).
  * Minimal or no attributes/methods.
  * Relationships depict conceptual associations.

---

### **2. Specification Perspective**

* Focus: Structure and behavior without code-level details.
* Audience: System architects, designers.
* Style:

  * Includes abstract classes, interfaces, and public methods.
  * Shows associations and inheritance.
  * Emphasizes **contract-based design**.

---

### **3. Implementation Perspective**

* Focus: Concrete, code-level details.
* Audience: Developers and software engineers.
* Style:

  * Shows all attributes and methods (with visibility).
  * Includes **data types, default values, constructors**.
  * Depicts all relationships: association, aggregation, composition, inheritance, dependency.

---

## **Relationships Between Classes**

1. **Association (USE-A)**

   * General relationship where one class uses another.
   * Example: `Teacher` ↔ `Student` (many-to-many).
   * UML: Solid line between classes.

2. **Aggregation (HAS-A)**

   * “Whole-part” relationship where parts can exist independently.
   * Example: `Department` has multiple `Professors`.
   * UML: Hollow diamond at the container class.

3. **Composition (Strong HAS-A)**

   * “Whole-part” relationship where the part cannot exist without the whole.
   * Example: `House` has `Rooms`.
   * UML: Filled diamond at the container side.

4. **Inheritance (IS-A)**

   * Subclass inherits from superclass.
   * Example: `Dog` is an `Animal`.
   * UML: Solid line with filled triangle pointing to parent.

5. **Realization (Implementation)**

   * A class implements an interface.
   * Example: `Circle` implements `Shape`.
   * UML: Dashed line with filled triangle pointing to interface.

6. **Dependency**

   * A class temporarily uses another class.
   * Example: `OrderService` depends on `PaymentService`.
   * UML: Dashed line with open arrow.

---

## **Summary Table**

| Relationship Type | Description                   | UML Notation              | Example                     |
| ----------------- | ----------------------------- | ------------------------- | --------------------------- |
| Association       | General “use-a” relationship  | Solid line                | Teacher–Student             |
| Aggregation       | Whole-part, independent parts | Hollow diamond            | Department–Professor        |
| Composition       | Whole-part, dependent parts   | Filled diamond            | House–Room                  |
| Inheritance       | “Is-a” hierarchy              | Solid line with triangle  | Dog–Animal                  |
| Realization       | Implements interface          | Dashed line with triangle | Circle–Shape                |
| Dependency        | Temporary usage               | Dashed line with arrow    | OrderService–PaymentService |



<img width="424" height="223" alt="image" src="https://github.com/user-attachments/assets/a8e97798-8cec-4e97-a876-da31da137adf" />

<img width="591" height="196" alt="image" src="https://github.com/user-attachments/assets/a54f05e2-ff18-4ae5-8cbb-a932a245f361" />

<img width="458" height="224" alt="image" src="https://github.com/user-attachments/assets/0e329e4d-2d1e-42ba-b9cc-b9cd1197127c" />

<img width="278" height="224" alt="image" src="https://github.com/user-attachments/assets/b302ef93-677e-4ead-bf0f-d18951481fee" />
<img width="278" height="224" alt="image" src="https://github.com/user-attachments/assets/3ce31793-dc8e-4ef7-afb7-42db6f51325c" />
<img width="1145" height="525" alt="image" src="https://github.com/user-attachments/assets/f55c2de5-21c8-4817-832a-f09fe925af4b" />


Here’s a clear example explaining **Association (USE-A)** with both **Java code** and its corresponding **UML Class Diagram** representation 👇

---

### 🧩 **Concept Recap**

**Association** represents a general relationship between two classes where one class **uses** or **interacts** with another.
It can be:

* **One-to-one**
* **One-to-many**
* **Many-to-many**

In simple terms:
➡️ *Class A uses Class B.*

---

### 💻 **Example in Java**

Let’s model a relationship between a `Teacher` and a `Student`.

```java
// Class representing a Student
public class Student {
    private String name;

    public Student(String name) {
        this.name = name;
    }

    public void displayInfo() {
        System.out.println("Student Name: " + name);
    }
}

// Class representing a Teacher
public class Teacher {
    private String teacherName;

    public Teacher(String teacherName) {
        this.teacherName = teacherName;
    }

    // Association: Teacher uses Student
    public void teach(Student student) {
        System.out.println(teacherName + " is teaching " + student);
        student.displayInfo();
    }
}

// Test the association
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Alice");
        Teacher t1 = new Teacher("Mr. John");

        // Association (USE-A)
        t1.teach(s1);
    }
}
```

---

### 🧭 **Explanation**

* The **`Teacher`** class has a method `teach(Student student)` that uses an object of the **`Student`** class.
* This indicates that **Teacher USES Student**.
* The association is **one-to-many** if a teacher can teach multiple students.

---

### 🧱 **UML Class Diagram**

```
+------------------+             +----------------+
|     Teacher      |             |    Student     |
+------------------+             +----------------+
| - teacherName: String |        | - name: String |
+------------------+             +----------------+
| + teach(student: Student): void | + displayInfo(): void |
+------------------+             +----------------+
            |
            |  uses
            |
            ----------------------------->
                    (Association)
```

---

### 🔍 **Key Takeaways**

* **Association** means *“uses-a”* relationship.
* Represented in UML by a **solid line** connecting two classes.
* **Directionality** can be shown with an arrow to indicate dependency.
* It’s a **loose relationship**, meaning both classes can exist independently.

---

Would you like me to extend this example to show **one-to-many association** (e.g., one teacher teaching multiple students) with its UML diagram as well?

Here’s a clear example explaining **Aggregation (HAS-A)** with **Java code** and its corresponding **UML Class Diagram** 👇

---

### 🧩 **Concept Recap**

**Aggregation** is a **“HAS-A”** relationship — a **whole-part** relationship where one class contains another class, but both can **exist independently**.

In simple words:
➡️ *A Department has Professors,* but even if the Department is deleted, Professors still exist.

---

### 💻 **Example in Java**

```java
// Class representing a Professor
public class Professor {
    private String name;

    public Professor(String name) {
        this.name = name;
    }

    public void display() {
        System.out.println("Professor Name: " + name);
    }
}

// Class representing a Department (HAS-A relationship with Professor)
import java.util.List;

public class Department {
    private String deptName;
    private List<Professor> professors;  // Aggregation

    public Department(String deptName, List<Professor> professors) {
        this.deptName = deptName;
        this.professors = professors;
    }

    public void showProfessors() {
        System.out.println("Department: " + deptName);
        for (Professor p : professors) {
            p.display();
        }
    }
}

// Test the Aggregation
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Professor p1 = new Professor("Dr. Smith");
        Professor p2 = new Professor("Dr. Alice");

        List<Professor> professors = new ArrayList<>();
        professors.add(p1);
        professors.add(p2);

        Department dept = new Department("Computer Science", professors);

        dept.showProfessors();
    }
}
```

---

### 🧭 **Explanation**

* The `Department` class **has** a list of `Professor` objects — that’s **Aggregation**.
* Professors can exist **independently** of the Department.
* If the Department object is destroyed, Professors still remain in memory.

---

### 🧱 **UML Class Diagram**

```
+-------------------+                 +----------------+
|    Department     |<>---------------|   Professor    |
+-------------------+                 +----------------+
| - deptName: String |                | - name: String |
| - professors: List<Professor> |     +----------------+
+-------------------+                 | + display(): void |
| + showProfessors(): void |          +----------------+
+-------------------+

<<aggregation>>  (HAS-A)
```

* The **hollow diamond (◊)** on the Department side represents **Aggregation**.
* The relationship line connects **Department** (whole) and **Professor** (part).

---

### 🔍 **Key Takeaways**

* **Aggregation = HAS-A relationship** where both can exist independently.
* Represented in UML with a **hollow diamond** at the *whole* side.
* Used when one class logically contains another but doesn’t control its lifetime.

---

Would you like me to continue with the next concept — **Composition (Strong HAS-A)** — using Java code and UML diagram next?
Perfect 👍 Let’s now go through **Composition (Strong HAS-A)** — a closer and more tightly bound version of aggregation — using a **real-world Java example** and a **UML Class Diagram**.

---

## 🧩 **Concept Recap**

**Composition** represents a **strong “HAS-A”** relationship.
It’s a *whole-part* relationship where the **part cannot exist without the whole**.

In simple words:
➡️ *A House has Rooms*, but if the House is destroyed, the Rooms are also gone.
Rooms cannot exist independently outside the House.

---

## 💻 **Example in Java**

```java
// Class representing a Room
public class Room {
    private String name;

    public Room(String name) {
        this.name = name;
    }

    public void showRoom() {
        System.out.println("Room: " + name);
    }
}

// Class representing a House (composition relationship with Room)
import java.util.ArrayList;
import java.util.List;

public class House {
    private String houseName;
    private List<Room> rooms;

    public House(String houseName) {
        this.houseName = houseName;
        this.rooms = new ArrayList<>();
    }

    // Adding room inside the house (House creates and owns Room)
    public void addRoom(String roomName) {
        Room room = new Room(roomName);
        rooms.add(room);
    }

    public void showHouse() {
        System.out.println("House: " + houseName);
        for (Room room : rooms) {
            room.showRoom();
        }
    }
}

// Test the Composition Relationship
public class Main {
    public static void main(String[] args) {
        House house = new House("Dream Villa");
        house.addRoom("Living Room");
        house.addRoom("Bedroom");
        house.addRoom("Kitchen");

        house.showHouse();

        // Once house object is destroyed, rooms cease to exist as well.
    }
}
```

---

## 🧠 **Explanation**

* The **House** object **owns** the **Room** objects — Rooms are created *inside* the House.
* When the **House** object is destroyed, the **Room** objects will also be destroyed.
* **Lifetime of Room** depends on **House**, making it a **Composition** relationship.

---

## 🧱 **UML Class Diagram**

```
+----------------+      ◆-------------+----------------+
|     House      |                    |      Room      |
+----------------+                    +----------------+
| - houseName: String |               | - name: String |
| - rooms: List<Room> |               +----------------+
+----------------+                    | + showRoom(): void |
| + addRoom(roomName: String): void | +----------------+
| + showHouse(): void |
+----------------+

<<composition>> (Strong HAS-A)
```

* The **filled diamond (◆)** on the `House` side represents **Composition**.
* It indicates that the **lifetime** of `Room` depends on `House`.

---

## 🔍 **Key Takeaways**

| Feature             | Aggregation          | Composition |
| ------------------- | -------------------- | ----------- |
| Lifetime            | Independent          | Dependent   |
| Diamond Type in UML | Hollow (◊)           | Filled (◆)  |
| Example             | Department–Professor | House–Room  |
| Ownership           | Shared               | Exclusive   |
| Dependency          | Weak                 | Strong      |

---

Would you like me to move next to **Inheritance (IS-A)** relationship with Java code and UML diagram?

Excellent 👏 Let’s now cover the **Inheritance (IS-A)** relationship — one of the most fundamental concepts in Object-Oriented Design — with a **real-world Java example** and a **UML class diagram**.

---

## 🧩 **Concept Recap**

**Inheritance (IS-A)** defines a relationship where a **child class (subclass)** derives from a **parent class (superclass)**.
The subclass **inherits** the parent’s attributes and methods, and can also **add or override** functionality.

In simple words:
➡️ *A Dog is an Animal.*
➡️ *A Car is a Vehicle.*

---

## 💻 **Example in Java**

```java
// Parent class (Super Class)
public class Animal {
    protected String name;

    public Animal(String name) {
        this.name = name;
    }

    public void eat() {
        System.out.println(name + " is eating...");
    }

    public void sleep() {
        System.out.println(name + " is sleeping...");
    }
}

// Child class (Sub Class)
public class Dog extends Animal {

    public Dog(String name) {
        super(name); // Call parent constructor
    }

    public void bark() {
        System.out.println(name + " is barking...");
    }
}

// Another child class
public class Cat extends Animal {

    public Cat(String name) {
        super(name);
    }

    public void meow() {
        System.out.println(name + " is meowing...");
    }
}

// Main class to test inheritance
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog("Buddy");
        dog.eat();   // inherited from Animal
        dog.bark();  // Dog-specific method

        Cat cat = new Cat("Whiskers");
        cat.sleep(); // inherited from Animal
        cat.meow();  // Cat-specific method
    }
}
```

---

## 🧠 **Explanation**

* **`Animal`** is the **parent class**, containing common attributes (`name`) and behaviors (`eat()`, `sleep()`).
* **`Dog`** and **`Cat`** are **child classes** that inherit from `Animal`.
* Each subclass can **reuse** and **extend** functionality — a key feature of **inheritance**.
* The relationship between `Animal` and `Dog` / `Cat` is **IS-A** → *Dog IS-A Animal*, *Cat IS-A Animal*.

---

## 🧱 **UML Class Diagram**

```
               +----------------+
               |    Animal      |
               +----------------+
               | - name: String |
               +----------------+
               | + eat(): void  |
               | + sleep(): void|
               +----------------+
                      ▲
                      |
     +----------------+----------------+
     |                                 |
+-------------+                  +-------------+
|     Dog     |                  |     Cat     |
+-------------+                  +-------------+
| + bark():void|                 | + meow():void|
+-------------+                  +-------------+
```

**UML Notation:**

* A **solid line with a hollow triangle** pointing from the subclass (`Dog`, `Cat`) to the superclass (`Animal`) represents **inheritance**.
* This denotes an **IS-A** relationship.

---

## 🔍 **Key Takeaways**

| Concept           | Inheritance                                     |
| ----------------- | ----------------------------------------------- |
| Relationship Type | IS-A                                            |
| UML Symbol        | Solid line with hollow triangle                 |
| Example           | Dog → Animal                                    |
| Purpose           | Reuse and extend behavior                       |
| Benefit           | Reduces code duplication, improves structure    |
| Risk              | Tight coupling — overuse can reduce flexibility |

---

Would you like me to continue with the next UML relationship — **Realization (Interface Implementation)** — along with Java example and UML diagram?
Perfect 👍 Let’s now explore the **Realization (Implementation)** relationship in UML — one of the most important relationships for designing flexible, modular, and extensible systems.

---

## 🧩 **Concept Recap — Realization (Implementation)**

**Definition:**
Realization represents the relationship between an **interface** and a **class** that **implements** it.

In simple words:
➡️ A class *agrees to perform* the behaviors declared in the interface.
➡️ The interface defines **what** must be done; the class defines **how** it’s done.

Think of it like a **contract**:

* The **interface** is the *contract* (what to do).
* The **class** is the *contractor* (how to do it).

---

## 💻 **Example in Java**

```java
// Interface - defines the contract
public interface PaymentProcessor {
    void processPayment(double amount);
}

// Class implementing the interface
public class CreditCardPayment implements PaymentProcessor {

    @Override
    public void processPayment(double amount) {
        System.out.println("Processing credit card payment of $" + amount);
    }
}

// Another class implementing the same interface
public class PayPalPayment implements PaymentProcessor {

    @Override
    public void processPayment(double amount) {
        System.out.println("Processing PayPal payment of $" + amount);
    }
}

// Main class to test the realization
public class Main {
    public static void main(String[] args) {
        PaymentProcessor payment1 = new CreditCardPayment();
        payment1.processPayment(150.0);

        PaymentProcessor payment2 = new PayPalPayment();
        payment2.processPayment(85.5);
    }
}
```

---

## 🧠 **Explanation**

* **`PaymentProcessor`** is an **interface** — it defines the *behavior* (method signature) but not the implementation.
* **`CreditCardPayment`** and **`PayPalPayment`** are **concrete classes** that implement this interface.
* The **main program** uses the interface type, not the concrete classes — this allows **dependency inversion** and **flexibility**.

If later you add **UPIPayment** or **BitcoinPayment**, you won’t need to modify existing code — just create a new class implementing `PaymentProcessor`.

---

## 🧱 **UML Class Diagram**

```
            +------------------------+
            | <<interface>>          |
            | PaymentProcessor       |
            +------------------------+
            | + processPayment(amount: double): void |
            +------------------------+
                     ▲           ▲
                     |           |
     +----------------+           +----------------+
     |                                     |
+---------------------+         +--------------------+
| CreditCardPayment   |         | PayPalPayment      |
+---------------------+         +--------------------+
| + processPayment(): void |    | + processPayment(): void |
+---------------------+         +--------------------+
```

**UML Notation:**

* The **dashed line with a hollow triangle** pointing to the interface (`PaymentProcessor`) represents **Realization**.
* The implementing classes (`CreditCardPayment`, `PayPalPayment`) are connected via this dashed arrow.

---

## 🔍 **Key Takeaways**

| Concept           | Realization (Implementation)                           |
| ----------------- | ------------------------------------------------------ |
| Relationship Type | Interface → Class                                      |
| UML Symbol        | Dashed line with hollow triangle                       |
| Example           | `CreditCardPayment` → `PaymentProcessor`               |
| Purpose           | Defines contracts and promotes loose coupling          |
| Benefit           | Easy to extend, test, and modify                       |
| Common Usage      | Service design, strategy pattern, dependency inversion |

---

Would you like me to continue with the next UML relationship — **Dependency (Uses)** — explained with a **Java code example and UML diagram**?
Awesome 😎 — let’s dive into the final UML relationship: **Dependency (Uses-A)**

---

## ⚙️ **Concept Recap — Dependency (Uses Relationship)**

**Definition:**
A **Dependency** represents a **“uses”** relationship between two classes —
one class **depends** on another **temporarily** to perform some operation.

👉 In other words:
A change in one class (the supplier) **may affect** the class that depends on it (the client).

Unlike aggregation or composition, **dependency is not a permanent relationship** — it’s *temporary* and *method-level*.

---

## 💡 **Real-life Analogy**

Imagine a **Customer** placing an order.
The customer **uses** a **PaymentService** to process the payment, but doesn’t “own” it.
The dependency exists *only while making a payment* — not permanently.

---

## 💻 **Example in Java**

```java
// Class that represents payment service
public class PaymentService {
    public void processPayment(double amount) {
        System.out.println("Payment of $" + amount + " processed successfully!");
    }
}

// Class that depends on PaymentService
public class Order {
    private String orderId;

    public Order(String orderId) {
        this.orderId = orderId;
    }

    // Dependency occurs here: Order temporarily uses PaymentService
    public void placeOrder() {
        System.out.println("Placing order ID: " + orderId);
        PaymentService paymentService = new PaymentService();
        paymentService.processPayment(250.75); // temporary use
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Order order = new Order("ORD123");
        order.placeOrder();
    }
}
```

---

## 🧠 **Explanation**

* `Order` **depends on** `PaymentService` to process the payment.
* The relationship exists **only during method execution** (`placeOrder()`), not as a class-level property.
* If `PaymentService` changes (say, new parameters), the `Order` class must adapt — this is why it’s called **dependency**.

---

## 🧱 **UML Class Diagram**

```
+--------------------+           +----------------------+
|      Order         |           |   PaymentService     |
+--------------------+           +----------------------+
| - orderId: String  |           |                      |
+--------------------+           +----------------------+
| + placeOrder(): void |         | + processPayment(amount: double): void |
+--------------------+           +----------------------+
             \
              \   <<uses>>
               \---------------------->
```

**UML Notation:**

* A **dashed line with an open arrow** (`----->`) represents a **dependency**.
* The arrow points **from the dependent class (Order)** to **the used class (PaymentService)**.
* The `<<uses>>` stereotype is often added to clarify the relationship.

---

## 🧩 **Key Differences (Dependency vs Aggregation vs Composition)**

| Relationship    | Lifespan   | Ownership        | UML Arrow      | Example              |
| --------------- | ---------- | ---------------- | -------------- | -------------------- |
| **Association** | Long-term  | Shared           | Solid line     | Teacher–Student      |
| **Aggregation** | Long-term  | Weak ownership   | Hollow diamond | Department–Professor |
| **Composition** | Long-term  | Strong ownership | Filled diamond | House–Room           |
| **Dependency**  | Short-term | No ownership     | Dashed arrow   | Order–PaymentService |

---

## ✅ **Key Takeaways**

* Dependency is **temporary** and exists usually at **method level**.
* Represents **uses**, not **has-a** or **is-a**.
* A change in the supplier class can impact the dependent class.
* Helps identify coupling between modules and supports cleaner designs.

---

Would you like me to make a **side-by-side summary table** of all UML relationships (Association, Aggregation, Composition, Inheritance, Realization, and Dependency) with **UML symbols and examples** next?
Perfect 👍 — here’s a **comprehensive side-by-side summary** of all **UML Class Relationships** with meanings, lifespans, ownership, UML notations, and real-world Java examples.

---

## 🧩 **UML Relationships Summary Table**

| **Relationship Type**            | **Meaning**                                                                       | **Lifespan / Ownership**      | **UML Notation**                         | **Java Example**              | **Real-World Analogy**                     |
| -------------------------------- | --------------------------------------------------------------------------------- | ----------------------------- | ---------------------------------------- | ----------------------------- | ------------------------------------------ |
| **Association (USE-A)**          | One class **uses or interacts** with another                                      | Long-term (shared)            | Solid line                               | `Teacher` ↔ `Student`         | A teacher teaches students                 |
| **Aggregation (HAS-A)**          | A class is made up of other classes, but **parts can exist independently**        | Whole–part (weak ownership)   | Hollow diamond at the whole side         | `Department` has `Professors` | Department–Professor                       |
| **Composition (Strong HAS-A)**   | A class is made up of other classes, but **parts cannot exist without the whole** | Whole–part (strong ownership) | Filled diamond at the whole side         | `House` has `Rooms`           | House–Room                                 |
| **Inheritance (IS-A)**           | Subclass inherits attributes and methods of superclass                            | Permanent relationship        | Solid line with closed (filled) triangle | `Dog` extends `Animal`        | Dog is an Animal                           |
| **Realization (Implementation)** | Class implements interface behavior                                               | Permanent contract            | Dashed line with closed triangle         | `Circle` implements `Shape`   | Class agreeing to perform defined behavior |
| **Dependency (USES)**            | One class **temporarily uses** another to perform an operation                    | Temporary (no ownership)      | Dashed line with open arrow              | `Order` uses `PaymentService` | Customer uses payment service              |

---

## 🧠 **Visual UML Summary Overview**

```
[Association]      A ─────────── B                (Teacher ─ Student)
[Aggregation]      A ◇────────── B                (Department ◇─ Professor)
[Composition]      A ◆────────── B                (House ◆─ Room)
[Inheritance]      A ─────────▷ B                 (Dog ─▷ Animal)
[Realization]      A - - - - -▷ B                 (Circle - -▷ Shape)
[Dependency]       A - - - - -▶ B                 (Order - -▶ PaymentService)
```

---

## 💻 **Quick Java Code References**

| **Type**        | **Example Code Snippet**                                                        |
| --------------- | ------------------------------------------------------------------------------- |
| **Association** | `Teacher teaches Student` via reference fields.                                 |
| **Aggregation** | `Department` holds a `List<Professor>`, but professors can exist independently. |
| **Composition** | `House` creates and destroys its `Room` objects internally.                     |
| **Inheritance** | `class Dog extends Animal` — Dog inherits Animal’s behavior.                    |
| **Realization** | `class Circle implements Shape` — Circle implements Shape interface.            |
| **Dependency**  | `Order` method calls `PaymentService` temporarily to process payments.          |

---

## ✅ **Key Takeaways**

* **Association, Aggregation, and Composition** → Represent **“Has-A”** relationships (different ownership levels).
* **Inheritance and Realization** → Represent **“Is-A”** relationships.
* **Dependency** → Represents **“Uses-A”** (temporary) relationships.
* Each relationship helps visualize **coupling**, **ownership**, and **lifetime dependencies** between classes in UML.

---

Would you like me to create a **diagram image (UML visual)** summarizing all these relationships side-by-side (for easy inclusion in your notes or PDF)?

