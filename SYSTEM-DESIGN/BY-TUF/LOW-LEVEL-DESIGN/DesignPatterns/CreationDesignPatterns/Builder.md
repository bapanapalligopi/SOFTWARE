**Builder Design Pattern**

### **Builder Pattern**

The **Builder Pattern** is a **creational design pattern** that separates the construction of a complex object from its representation. This allows you to create different representations of an object using the same construction process.

**Formal Definition:**

> “Builder pattern builds a complex object step by step. It separates the construction of a complex object from its representation so that the same construction process can create different representations.”

---

### **Simple Explanation**

Imagine you're ordering a **custom burger**. You pick your bun, patty, cheese, toppings, and sauces — step by step.
The chef follows your instructions and builds your burger accordingly.
This is exactly what the Builder Pattern does — it lets you **build complex objects in a controlled, flexible, and readable way.**

---

### **Real-Life Analogy: Custom Pizza Order**

When ordering a pizza online, you pick:

* Size
* Crust type
* Toppings
* Cheese
* Sauce

Each customer follows the same process but ends up with a completely different pizza.
That’s the **Builder Pattern** — a step-by-step construction process with customizable options.

---

### **The Problem**

Let’s say we want to create a `BurgerMeal` object in Java with:

* Mandatory fields: `bun`, `patty`
* Optional fields: `cheese`, `toppings`, `sides`

If we use constructors, we run into multiple issues:

#### **Problems with Constructor Approach**

1. **Hard to Read and Maintain:**
   Users must remember the order of parameters.
2. **Unnecessary null values:**
   Even unused fields must be passed as `null`.
3. **NullPointerException risk:**
   If optional fields are accessed without checks.
4. **Too Many Overloaded Constructors:**
   Leads to **Telescoping Constructor Anti-Pattern**.
5. **No Step-by-Step Construction:**
   The whole object must be built at once.

---

### **Telescoping Constructor Anti-Pattern**

```java
public class BurgerMeal {
    private String bun;
    private String patty;
    private boolean cheese;
    private String side;
    
    public BurgerMeal(String bun, String patty) {
        this(bun, patty, false, null);
    }
    
    public BurgerMeal(String bun, String patty, boolean cheese) {
        this(bun, patty, cheese, null);
    }
    
    public BurgerMeal(String bun, String patty, boolean cheese, String side) {
        this.bun = bun;
        this.patty = patty;
        this.cheese = cheese;
        this.side = side;
    }
}
```

This becomes unreadable and unmaintainable as the number of optional parameters grows.

---

### **Solution: Builder Pattern**

Instead of multiple constructors, we use a **Builder Class** that constructs the object step by step.

#### **Java Implementation**

```java
public class BurgerMeal {
    private final String bun;
    private final String patty;
    private final boolean cheese;
    private final String side;
    private final String toppings;

    private BurgerMeal(BurgerBuilder builder) {
        this.bun = builder.bun;
        this.patty = builder.patty;
        this.cheese = builder.cheese;
        this.side = builder.side;
        this.toppings = builder.toppings;
    }

    public static class BurgerBuilder {
        private final String bun;
        private final String patty;
        private boolean cheese;
        private String side;
        private String toppings;

        public BurgerBuilder(String bun, String patty) {
            this.bun = bun;
            this.patty = patty;
        }

        public BurgerBuilder withCheese(boolean cheese) {
            this.cheese = cheese;
            return this;
        }

        public BurgerBuilder withSide(String side) {
            this.side = side;
            return this;
        }

        public BurgerBuilder withToppings(String toppings) {
            this.toppings = toppings;
            return this;
        }

        public BurgerMeal build() {
            return new BurgerMeal(this);
        }
    }

    @Override
    public String toString() {
        return "BurgerMeal [bun=" + bun + ", patty=" + patty + ", cheese=" + cheese + 
               ", side=" + side + ", toppings=" + toppings + "]";
    }
}

// Client code
public class BuilderPatternDemo {
    public static void main(String[] args) {
        BurgerMeal burger = new BurgerMeal.BurgerBuilder("Sesame", "Beef")
                              .withCheese(true)
                              .withSide("Fries")
                              .withToppings("Lettuce, Tomato")
                              .build();

        System.out.println(burger);
    }
}
```

---

### **Understanding the Code**

| Aspect                      | Description                                                               |
| --------------------------- | ------------------------------------------------------------------------- |
| **Private Constructor**     | Prevents direct instantiation from outside the class.                     |
| **Nested Builder Class**    | Handles object construction logic.                                        |
| **Fluent API**              | Allows chaining (`.withCheese().withSide()`) for readability.             |
| **Selective Configuration** | Only required fields are mandatory; optional ones are added step-by-step. |
| **Immutable Object**        | The built object is final and cannot be modified later.                   |

---

### **Why It’s Better**

| Aspect              | Constructor Approach    | Builder Pattern                |
| ------------------- | ----------------------- | ------------------------------ |
| **Readability**     | Poor (nulls, long args) | Excellent (fluent, expressive) |
| **Flexibility**     | Low                     | High                           |
| **Maintainability** | Hard to scale           | Easy to extend                 |
| **Safety**          | High chance of nulls    | Controlled instantiation       |

---

### **When to Use the Builder Pattern**

✅ Use when:

* Objects have **many optional fields**.
* You want **immutable objects**.
* You want **clean, readable, and flexible object creation**.

❌ Avoid when:

* The object has **few fields** (1–2).
* You **don’t need customization** or immutability.

---

### **Pros and Cons**

**Pros**

* Prevents telescoping constructors.
* Ensures immutability.
* Clean, readable, and maintainable code.
* Excellent for complex configurations.

**Cons**

* More boilerplate code.
* Overkill for small classes.
* Requires an additional Builder class.

---

### **Real-World Examples**

1. **Lombok’s @Builder (Java)**

   ```java
   @Builder
   public class Employee {
       private String name;
       private int age;
       private String department;
   }
   ```

   Then you can create an object like:

   ```java
   Employee emp = Employee.builder()
                          .name("John")
                          .age(30)
                          .department("IT")
                          .build();
   ```

2. **Amazon Cart Configuration**
   When adding an item to your cart, you specify quantity, size, color, and delivery preferences — all optional fields built step by step using a **Builder-like approach** internally.

---

### **UML Class Diagram**

```
           +-------------------+
           |   BurgerMeal      |
           +-------------------+
           | - bun             |
           | - patty           |
           | - cheese          |
           | - side            |
           | - toppings        |
           +-------------------+
           | + toString()      |
           +-------------------+
                    ^
                    |
           +----------------------+
           |   BurgerBuilder      |
           +----------------------+
           | - bun, patty         |
           | - cheese, side, top. |
           +----------------------+
           | + withCheese()       |
           | + withSide()         |
           | + withToppings()     |
           | + build()            |
           +----------------------+
```

---

### **Conclusion**

The **Builder Pattern** is a powerful and flexible solution for constructing complex objects step by step.
It improves **code readability**, **maintainability**, and **safety**, while supporting **immutability** and **fluent APIs**.
Although slightly verbose, it’s widely used in frameworks and enterprise applications where clarity and flexibility matter.


Yes ✅ — in **Java**, you can replace most of the boilerplate Builder code with the **Lombok `@Builder` annotation**.

### 💡 **Lombok @Builder**

The `@Builder` annotation automatically generates:

* A **builder class** (inner static class)
* All **builder methods** (`.builder()`, `.withField()`, `.build()`)
* A **private constructor** to enforce immutability

Here’s how it simplifies the code 👇

#### ✅ Traditional Builder (manual code)

```java
BurgerMeal burger = new BurgerMeal.BurgerBuilder("Sesame", "Beef")
        .withCheese(true)
        .withSide("Fries")
        .withToppings("Lettuce, Tomato")
        .build();
```

#### ✅ Same with Lombok `@Builder`

```java
import lombok.Builder;
import lombok.ToString;

@Builder
@ToString
public class BurgerMeal {
    private String bun;
    private String patty;
    private boolean cheese;
    private String side;
    private String toppings;
}
```

**Client Code:**

```java
public class BuilderDemo {
    public static void main(String[] args) {
        BurgerMeal burger = BurgerMeal.builder()
                .bun("Sesame")
                .patty("Beef")
                .cheese(true)
                .side("Fries")
                .toppings("Lettuce, Tomato")
                .build();

        System.out.println(burger);
    }
}
```

---

### ⚙️ How It Works

* Lombok automatically generates:

  * A static `builder()` method
  * A nested `Builder` class with all the `withField()` methods
  * The final `build()` method
* It keeps the code clean and concise, just like the **manual Builder pattern**, but with zero boilerplate.

---

### ⚠️ Notes

* You need **Project Lombok** dependency:

  ```xml
  <!-- Maven -->
  <dependency>
      <groupId>org.projectlombok</groupId>
      <artifactId>lombok</artifactId>
      <version>1.18.34</version>
      <scope>provided</scope>
  </dependency>
  ```
* Works at **compile time** — your IDE (like IntelliJ or Eclipse) must have Lombok plugin enabled.
* Can be combined with other Lombok annotations like `@Getter`, `@Setter`, `@AllArgsConstructor`, and `@ToString`.

---

Would you like me to show how to combine `@Builder` with `@Value` (for immutable objects, like a record-style builder)?

