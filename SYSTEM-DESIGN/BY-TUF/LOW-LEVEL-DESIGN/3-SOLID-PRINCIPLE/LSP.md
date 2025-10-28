Excellent 👍 — here’s your **exact Liskov Substitution Principle (LSP)** content, preserved word-for-word but perfectly formatted and styled for clarity, with **Java examples included** exactly as intended.

---

# **Liskov Substitution Principle (LSP)**

## **Introduction**

There is a set of five principles for writing clean, scalable, maintainable object-oriented code.
These principles are known as **SOLID principles**.
The **L** in SOLID stands for **Liskov Substitution Principle**.

---

## **Definition:**

> If **S** is a subtype of **T**, then objects of type **T** may be replaced with objects of type **S** without altering the correctness of the program.

This means that any subclass should be **substitutable** for its parent class without breaking the functionality.

Think of it like this:
If you write code using a parent class (say `Shape`), and later swap in a child class (using the child class object in place of the parent class object) (like `Circle`), the code should still work without errors or unexpected behavior.

If the subclass changes behavior in a way that breaks expectations, it violates **LSP**.

---

## **Real-life Analogy**

Imagine you run a **pet hotel**, and you have a general policy —
“Any pet staying here must be able to be fed, walked, and groomed.”

So you design your hotel to handle pets — and you've had **dogs, cats, and rabbits** as guests, and things work fine.

### **Problem**

Assume someone brings in a **pet snake**. Here are the issues:

* You try to walk it. Can't.
* You try to groom it. Doesn't make sense.
* You offer pet food. Snake needs live mice.

Suddenly, your normal pet hotel process breaks.
Your system expected all pets to behave like dogs or cats, but this snake breaks the assumptions.
This creates an **LSP Violation**.

---

### **A Valid Substitution**

If instead someone brings in a **pet hamster** — it still eats food, needs care, and maybe doesn't walk outside, but it still fits within the expected “pet” behavior.
You just make a minor adjustment (like putting it in a wheel instead of walking it).
Still fine — no big surprises.

---

### **Understanding**

The pet hotel needs to trust that any "pet" will behave in expected ways.
If a new pet completely changes the rules, the whole system becomes fragile.

That's exactly what the **Liskov Substitution Principle** protects us from in software —
making sure substituting one thing for another doesn't break the expected behavior.

---

## **Example: LSP Violation**

Let's illustrate this with the classic **Rectangle–Square example**, which is a famous LSP violation case.
Consider the code given below:

```java
// Base class
class Rectangle {
    protected int width;
    protected int height;

    public void setWidth(int width) {
        this.width = width;
    }

    public void setHeight(int height) {
        this.height = height;
    }

    public int getArea() {
        return width * height;
    }
}

// Subclass (Violation)
class Square extends Rectangle {
    @Override
    public void setWidth(int width) {
        this.width = width;
        this.height = width; // Forces height = width
    }

    @Override
    public void setHeight(int height) {
        this.height = height;
        this.width = height; // Forces width = height
    }
}

public class Main {
    public static void printArea(Rectangle r) {
        r.setWidth(5);
        r.setHeight(10);
        System.out.println("Expected area = 50, Actual area = " + r.getArea());
    }

    public static void main(String[] args) {
        Rectangle rect = new Rectangle();
        printArea(rect); // ✅ Works fine

        Rectangle square = new Square();
        printArea(square); // ❌ Violates LSP
    }
}
```

---

### **Violation**

**Expected Output:** `50`
**Actual Output:** `100` (since both width and height became `10`)

So, the `Square` violates **LSP** because it changes the behavior of `setWidth()` and `setHeight()`, breaking the assumptions of the parent class.

---

## **Need of LSP**

Consider the example of a **Notification system**:

```java
// Base class
class Notification {
    public void sendNotification(String message) {
        System.out.println("Sending generic notification: " + message);
    }
}
```

Assume we wish to introduce some new types of notifications, say **Email Notification** or **Text Notification**.
In such a case, we can create a new class for each type of notification, and we can easily extend the system without breaking existing code using the **Liskov Substitution Principle**.

---

### ✅ **LSP-Compliant Example**

```java
// Subclass 1
class EmailNotification extends Notification {
    @Override
    public void sendNotification(String message) {
        System.out.println("Sending Email: " + message);
    }
}

// Subclass 2
class TextNotification extends Notification {
    @Override
    public void sendNotification(String message) {
        System.out.println("Sending Text Message: " + message);
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Notification email = new EmailNotification();
        Notification text = new TextNotification();

        email.sendNotification("Your order has been shipped!");
        text.sendNotification("Your OTP is 123456.");
    }
}
```

Here, the only change needed for introducing two different types of notifications is to create two subclasses of the `Notification` class with overridden `sendNotification()` methods.
The main class can remain unchanged — the only change is **which object we instantiate**.

This is the **power of LSP**.
It allows us to **extend our system without breaking existing code**.

---

## **Why Does LSP Matter?**

When **LSP** is violated, the code becomes:

* ❌ **Unpredictable:** Code relying on base class assumptions will break with certain subclasses.
* ❌ **Hard to Maintain:** Adding new subclasses requires rechecking all usages.
* ❌ **Bug-Prone:** Runtime errors, wrong outputs, or inconsistent behavior.
* ❌ **Less Reusable:** Substituting child objects becomes dangerous.
* ❌ **Tightly Coupled:** Client code ends up getting tightly coupled to specific types, making it less maintainable.

Hence, to avoid these problems while working on a huge codebase, it is recommended to follow the **Liskov Substitution Principle (LSP)** wherever possible.

---

## **How to Spot LSP Violations?**

Ask yourself these questions:

* Does the subclass override methods in a way that changes meaning or assumptions?
* Can I replace the base class with the subclass everywhere without side effects?
* Does the subclass throw unexpected exceptions or return wrong values?
* Does the subclass weaken any preconditions or strengthen postconditions?

If the answer to any of these questions is **“yes”**, there might be an **LSP violation** in the code.

---

## **Key Principles to Follow**

To avoid LSP violations:

1. **Subclasses should honor the contract** (expectations) of the parent class.
2. **Avoid overriding methods** in a way that changes behavior drastically.
3. **Prefer composition over inheritance** when possible.
4. Think in terms of **interfaces and behavioral compatibility**.
5. **Subclass should only extend, not restrict behavior.**

---

Would you like me to continue next with the **I — Interface Segregation Principle (ISP)** in the same style — including real-life analogy, definition, and Java examples (good & bad)?
