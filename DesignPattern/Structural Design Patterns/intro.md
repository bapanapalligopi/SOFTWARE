Got it 👍 Let’s break this down step by step.

You’re asking about **Structural Design Patterns** — one of the **three main categories of GoF (Gang of Four) design patterns**.

---

# 🌉 **Structural Design Patterns – Explained**

Structural Design Patterns focus on **how classes and objects are combined** to form **bigger, more flexible, and efficient structures**.
👉 Think of them as **“blueprints for building strong bridges between objects.”**

They help solve problems like:

* Making two incompatible classes work together.
* Adding new features without breaking existing code.
* Reducing memory use by sharing objects.
* Providing controlled or simplified access to complex subsystems.

---

## 🔑 **Types of Structural Design Patterns**

### 1. **Adapter Pattern** (a.k.a Wrapper)

* **Purpose:** Convert the interface of one class into another interface clients expect.
* **Analogy:** Think of a **power adapter** (US plug into EU socket).
* **Use Case:** When two systems are incompatible but need to work together.
* **Example:** Making a legacy `OldPaymentGateway` work with a new `NewPaymentProcessor`.

---

### 2. **Bridge Pattern**

* **Purpose:** Separate **abstraction** (what you do) from **implementation** (how it’s done).
* **Analogy:** A **remote control** (abstraction) works with any **TV brand** (implementation).
* **Use Case:** When you want to vary abstraction and implementation independently.
* **Example:** A `Shape` (circle, square) can use different `Color` implementations (red, blue).

---

### 3. **Composite Pattern**

* **Purpose:** Treat **individual objects** and **groups of objects** uniformly.
* **Analogy:** A **folder structure** – files and folders can be handled the same way.
* **Use Case:** Represent part-whole hierarchies.
* **Example:** A `Directory` can contain both `Files` and other `Directories`.

---

### 4. **Decorator Pattern**

* **Purpose:** Dynamically add behavior to objects **at runtime** without altering their structure.
* **Analogy:** A **Christmas tree** 🎄 – you start with a tree and keep adding decorations.
* **Use Case:** When you need flexible, extensible functionality.
* **Example:** Adding compression/encryption to a `DataStream`.

---

### 5. **Facade Pattern**

* **Purpose:** Provide a **simplified interface** to a complex subsystem.
* **Analogy:** A **universal remote** controlling multiple devices behind the scenes.
* **Use Case:** Hide complexities and expose only what’s necessary.
* **Example:** A `BankFacade` that internally calls multiple systems (account, loan, credit).

---

### 6. **Flyweight Pattern**

* **Purpose:** Reduce memory usage by sharing common state between many similar objects.
* **Analogy:** A **chess game** ♟️ – only one piece object per type is shared across the board.
* **Use Case:** Large numbers of similar objects (e.g., game characters, icons).
* **Example:** Sharing intrinsic properties of `Tree` objects in a forest.

---

### 7. **Proxy Pattern**

* **Purpose:** Provide a **placeholder or surrogate** for another object to control access to it.
* **Analogy:** A **credit card** 💳 acts as a proxy for your bank account.
* **Use Case:** Lazy loading, security control, logging, caching.
* **Example:** A `ProxyImage` loads the real `Image` only when needed.

---

## 📌 Summary Table

| Pattern   | What it Does                           | Real-life Analogy          |
| --------- | -------------------------------------- | -------------------------- |
| Adapter   | Converts interface                     | Power adapter              |
| Bridge    | Separates abstraction & implementation | Remote + TV                |
| Composite | Treats group & single objects the same | File system                |
| Decorator | Adds behavior dynamically              | Christmas tree decorations |
| Facade    | Simplifies a complex subsystem         | Universal remote           |
| Flyweight | Reuses shared objects                  | Chess pieces               |
| Proxy     | Acts as a placeholder/control          | Credit card                |

---

👉 So, **Structural patterns = how to connect and arrange objects in a flexible and efficient way**.

Would you like me to also **give Java code examples** (like we did with Builder) for each of these 7 patterns? That way you’ll have a ready reference.
