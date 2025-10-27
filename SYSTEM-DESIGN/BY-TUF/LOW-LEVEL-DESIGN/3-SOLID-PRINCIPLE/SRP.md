Sure — here’s **exactly what you gave**, formatted neatly while keeping every word, structure, and detail intact 👇

---

# **Single Responsibility Principle (SRP)**

## **Introduction**

There is a set of five principles for writing clean, scalable, maintainable object-oriented code. These principles are known as **SOLID principles**. The **S** in SOLID stands for **Single Responsibility Principle**.

---

## **Definition:**

A class should have only one reason to change.
In other words, a class should only have **one job, one responsibility, and one purpose.**

If a class takes more than one responsibility, it becomes **coupled**. This means that if one responsibility changes, the other responsibilities may also be affected, leading to a ripple effect of changes throughout the codebase.

---

## **Real-life Analogy**

Imagine a **chef** who is responsible for cooking, cleaning, serving food and ordering groceries.
If the chef is busy cleaning, they can't focus on cooking, and the quality of the food may suffer.

Instead, different people should handle each task:

* One person cooks (**chef**)
* Another cleans (**cleaner**)
* A third serves (**waiter**)
* Another orders groceries (**manager**)

This way, each person can focus on their specific responsibility, leading to better results overall.

---

## **Significance of SRP**

Let us understand this with the example of **TUF+ compiler**.
Currently, the TUF+ compiler does the following things:

1. Adds driver code
2. Performs syntax check
3. Runs code with already fed test cases
4. Stores the output in Database
5. Returns the necessary output to the user

Now, implementing all the above functionalities in a single `TUFplusCompiler` class would violate the **Single Responsibility Principle (SRP)**.

---

Instead, we can break it down into smaller classes, each with a single responsibility:

* **DriverCodeGenerator** → Responsible for adding driver code.
* **SyntaxChecker** → Responsible for performing syntax checks.
* **TestRunner** → Responsible for running code with test cases.
* **DatabaseManager** → Responsible for storing output in the database.
* **UserOutputHandler** → Responsible for returning output to the user.

Another class named **Coordinator** can be added to coordinate between all these classes/modules.

By following the **Single Responsibility Principle**, we can make the code **more modular, easier to maintain, and less prone to bugs.**
Each class can be modified or replaced independently without affecting the others.

---

## **Advantages of SRP**

* **Improved Maintainability:**
  Changes in one part of the system won't affect other parts, making it easier to maintain and update.

* **Enhanced Readability:**
  Smaller, focused classes are easier to read and understand.

* **Better Reusability:**
  Classes with a single responsibility can be reused in different contexts without bringing unnecessary dependencies.

* **Facilitates Testing:**
  Smaller classes are easier to test, as they have fewer dependencies and responsibilities.

* **Lower Risk in Changes:**
  Since each class handles only one concern, changes made to it are less likely to cause unintended side effects in other parts of the system.

---

## **Common Mistakes When Violating SRP**

There are a few common mistakes that developers make when violating the **Single Responsibility Principle (SRP)**. Here are some examples:

* **Mixing Database Logic with Business Logic:**
  Putting both data access (e.g., SQL, JDBC) and core business rules in the same class.
  This makes it hard to change the database layer without affecting business logic.

* **Coupling UI Code with Business Logic:**
  Embedding application logic directly in the UI layer.
  This makes it tedious to change the UI without affecting the underlying logic.

---

## **Note**

An important question to ask is:
**"Is SRP just for classes?"**

The answer is **no**. SRP can be applied to **methods, modules, microservices**, and even entire systems.
The key is to ensure that each component has a single responsibility and that changes in one area do not affect others unnecessarily.

Hence, **SRP is not just for classes.**
It’s a **mindset** you can apply from the smallest method to the largest system design.

---

Perfect 👌 Let’s extend your **Single Responsibility Principle (SRP)** explanation with a **clear, real-world Java example** — showing both a *violation* and a *proper SRP-compliant refactor*.

---

# 🧱 **Single Responsibility Principle (SRP) — With Java Example**

---

## ⚠️ **Without SRP (Bad Example)**

Here’s a single class that does *too many things* — user management, saving to database, and sending emails — all in one place:

```java
public class UserService {

    public void registerUser(String username, String email, String password) {
        // 1️⃣ Validate user data
        if (username == null || email == null || password == null) {
            throw new IllegalArgumentException("Invalid data");
        }

        // 2️⃣ Save user data to database
        System.out.println("Saving user " + username + " to database...");

        // 3️⃣ Send welcome email
        System.out.println("Sending welcome email to " + email);
    }
}
```

### ❌ Problems:

* The class has **multiple responsibilities**:

  * Validating data
  * Interacting with the database
  * Sending emails
* If you need to change how emails are sent, you risk breaking registration logic.
* It violates **SRP**, making the code harder to maintain, test, or extend.

---

## ✅ **With SRP (Good Example)**

Now let’s break this into multiple classes — each handling a **single responsibility**.

### Step 1: Create a `User` model

```java
public class User {
    private String username;
    private String email;
    private String password;

    public User(String username, String email, String password) {
        this.username = username;
        this.email = email;
        this.password = password;
    }

    public String getUsername() { return username; }
    public String getEmail() { return email; }
    public String getPassword() { return password; }
}
```

---

### Step 2: Create a `UserValidator` class

```java
public class UserValidator {
    public boolean isValid(User user) {
        return user.getUsername() != null && user.getEmail() != null && user.getPassword() != null;
    }
}
```

---

### Step 3: Create a `UserRepository` class

```java
public class UserRepository {
    public void save(User user) {
        System.out.println("Saving user " + user.getUsername() + " to database...");
    }
}
```

---

### Step 4: Create an `EmailService` class

```java
public class EmailService {
    public void sendWelcomeEmail(String email) {
        System.out.println("Sending welcome email to " + email);
    }
}
```

---

### Step 5: Create the main `UserService` class

```java
public class UserService {
    private UserValidator validator;
    private UserRepository repository;
    private EmailService emailService;

    public UserService(UserValidator validator, UserRepository repository, EmailService emailService) {
        this.validator = validator;
        this.repository = repository;
        this.emailService = emailService;
    }

    public void registerUser(User user) {
        if (validator.isValid(user)) {
            repository.save(user);
            emailService.sendWelcomeEmail(user.getEmail());
        } else {
            System.out.println("Invalid user details!");
        }
    }
}
```

---

### Step 6: Main Program

```java
public class Main {
    public static void main(String[] args) {
        User user = new User("JohnDoe", "john@example.com", "12345");

        UserValidator validator = new UserValidator();
        UserRepository repository = new UserRepository();
        EmailService emailService = new EmailService();

        UserService service = new UserService(validator, repository, emailService);
        service.registerUser(user);
    }
}
```

---

## 💡 **Benefits of SRP in This Example**

✅ Each class has **one responsibility**:

* `UserValidator` → validates users
* `UserRepository` → handles persistence
* `EmailService` → handles notifications
* `UserService` → coordinates the workflow

✅ Easy to modify or test independently — for example:

* You can change the email logic without touching the database code.
* You can mock `UserRepository` for unit testing.

✅ The code is now **cleaner, modular, and extensible.**

---

Would you like me to include this Java SRP example in a **formatted PDF** with your earlier explanation (definition, analogy, advantages, etc.) — as a professional “SRP Study Note”?
