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
