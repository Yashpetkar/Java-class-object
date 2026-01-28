# Java-class-object

---

# ☕ Basic Java Classes – Beginner Friendly Guide

This repository is created to help **beginners understand Java Classes and Objects** in a **simple and practical way**.
It is especially useful for **first-year students** and those new to **Object-Oriented Programming (OOP)**.

---

## 📌 What You Will Learn from This Repository

* What is a **Class** in Java
* What is an **Object**
* How to create a **class**
* How to create and use **objects**
* Understanding **variables** and **methods** inside a class
* Running your **first Java class program**

---

## 🧠 What is a Class in Java?

A **class** is a **blueprint or template** used to create objects.

👉 Think of a **Class** like a **design of a house**
👉 An **Object** is the **actual house built using that design**

### Example:

* Class → `Student`
* Objects → `student1`, `student2`

---

## 🧠 What is an Object?

An **object** is a **real instance of a class**.
It represents real-world entities and uses the variables and methods defined in the class.

---

## 🗂 Project Structure

```
Basic-Java-Class/
│
├── Student.java
├── Calculator.java
└── README.md
```

---

## 🧪 Example 1: Simple Student Class

### 📄 Student.java

```java
class Student {

    // Data members (variables)
    int id;
    String name;

    // Method
    void display() {
        System.out.println("Student ID: " + id);
        System.out.println("Student Name: " + name);
    }

    // Main method
    public static void main(String[] args) {

        // Creating object of Student class
        Student s1 = new Student();

        // Assigning values
        s1.id = 101;
        s1.name = "Rahul";

        // Calling method
        s1.display();
    }
}
```

---

### 🔍 Explanation

* `class Student` → Defines a class
* `int id`, `String name` → Data members (variables)
* `void display()` → Method inside the class
* `Student s1 = new Student();` → Object creation
* `s1.id = 101;` → Assigning values using object
* `s1.display();` → Calling method using object

---

## 🧪 Example 2: Simple Calculator Class

### 📄 Calculator.java

```java
class Calculator {

    int a = 10;
    int b = 5;

    void add() {
        System.out.println("Addition: " + (a + b));
    }

    void subtract() {
        System.out.println("Subtraction: " + (a - b));
    }

    public static void main(String[] args) {

        Calculator calc = new Calculator();

        calc.add();
        calc.subtract();
    }
}
```

---

### 🔍 Explanation

* `Calculator` is a class
* `a` and `b` are variables
* `add()` and `subtract()` are methods
* `calc` is an object used to access methods

---

## ▶️ How to Run This Program

### Step 1: Install Java JDK

Make sure Java is installed:

```bash
java -version
```

### Step 2: Compile the Program

```bash
javac Student.java
```

### Step 3: Run the Program

```bash
java Student
```

---

# Method Call Stack in Java

Java is an **object-oriented, stack-based programming language**. During program execution, Java uses a **call stack** to manage method calls, local variables, and execution flow. Understanding the call stack is essential for debugging, performance optimization, and writing efficient programs.

---

## 📌 What is the Call Stack?

The **call stack** is a runtime data structure used by the **Java Virtual Machine (JVM)** to keep track of **active method calls**.

### Key Characteristics:

* Works on **LIFO (Last In, First Out)** principle
* Stores **method execution information**
* Automatically managed by the **JVM**

### Each method call creates a **stack frame** that stores:

* Local variables
* Parameters
* Return address
* Intermediate results

---

## 📌 How Does the Call Stack Work?

Whenever a method is called:

1. A **new stack frame** is created and pushed onto the call stack.
2. The method starts execution.
3. After execution completes, the stack frame is **popped out**.
4. Control returns to the **calling method**.

---

## 📌 Why is Call Stack Important?

* Manages **method execution flow**
* Supports **nested method calls**
* Enables **recursion**
* Helps in **debugging using stack trace**

---

## 📌 Method Call Stack Execution Flow Example

### Java Code Example

```java
public class CallStackExample {

    public static void D() {
        float d = 40.5f;
        System.out.println("In Method D");
    }

    public static void C() {
        double c = 30.5;
        System.out.println("In Method C");
    }

    public static void B() {
        int b = 20;
        C(); // Calling C
        System.out.println("In Method B");
    }

    public static void A() {
        int a = 10;
        B(); // Calling B
        System.out.println("In Method A");
    }

    public static void main(String[] args) {
        A(); // Start with function A
        D(); // Then call D
    }
}
```

---

## 📌 Step-by-Step Execution Flow

### Call Order:

```
main()
  → A()
      → B()
          → C()
```

### Execution Stack Movement:

1. `main()` pushed to stack
2. `A()` pushed
3. `B()` pushed
4. `C()` pushed
5. `C()` completes → popped
6. `B()` continues → popped
7. `A()` continues → popped
8. Back to `main()`
9. `D()` pushed → popped

---

## 📌 Call Stack Visualization

```
|   D()   |   ← Last Called
|   A()   |
|   B()   |
|   C()   |   ← First Completed
| main() |
```

---

## 📌 Program Output

```
In Method C
In Method B
In Method A
In Method D
```

### Explanation:

* `C()` executes first because it is the **deepest nested call**
* Then `B()`
* Then `A()`
* Finally `D()` executes after `A()` completes

---

## 📌 Real-Life Analogy

Think of the call stack like a **stack of plates** 🍽️:

* You place plates one over another
* You remove the **topmost plate first**

Similarly, the **last called method finishes first**.

---

## 📌 Stack Overflow Error

If too many methods are called (especially in **infinite recursion**), the stack becomes full, leading to:

```
Exception in thread "main" java.lang.StackOverflowError
```

---

# Initialize Object Using Method in Java

This example demonstrates **how to initialize object data using methods (functions) in Java**. Instead of using constructors, we assign values to variables using a **setter method** and display them using a **getter method**.

---

## 📌 Objective

* Understand how to **initialize variables using methods**
* Learn the concept of **setter and getter methods**
* Understand **static variables and static methods**

---

## 📌 Java Program

```java
public class Geeks {

    static String name;
    static float price;

    static void set(String n, float p) {
        name = n;
        price = p;
    }

    static void get() {
        System.out.println("Software name is: " + name);
        System.out.println("Software price is: " + price);
    }

    public static void main(String[] args) {
        Geeks.set("Visual Studio", 0.0f);
        Geeks.get();
    }
}
```

---

## 📌 Explanation

### 1️⃣ Static Variables

```java
static String name;
static float price;
```

* These are **class-level variables**
* Shared among all objects of the class

---

### 2️⃣ Setter Method

```java
static void set(String n, float p)
```

* Assigns values to variables
* Used to **initialize object data**

---

### 3️⃣ Getter Method

```java
static void get()
```

* Displays the stored values

---

### 4️⃣ Main Method

```java
Geeks.set("Visual Studio", 0.0f);
Geeks.get();
```

* Calls the setter method to assign values
* Calls the getter method to print values

---

## 📌 Program Output

```
Software name is: Visual Studio
Software price is: 0.0
```

---

## 📌 Execution Flow

```
main()
  → set("Visual Studio", 0.0)
      → assign values
  → get()
      → print values
```

---

## 📌 Key Concepts Used

* Static Variables
* Static Methods
* Method-based Initialization
* Getter and Setter Methods

---

## 📌 Advantages of Method-based Initialization

* Better **control over data assignment**
* Improves **code readability and reusability**
* Supports **data validation before assignment**

---

## 📌 Real-Life Example

Like entering product details in a form:

* `set()` → store product info
* `get()` → display product info

---


# Java OOP – Access Modifiers (Detailed Lecture Notes)

> **Instructor:** Yash Petkar
> **Topic:** Java Object-Oriented Programming – Access Modifiers
> **Level:** Beginner to Intermediate
> **Use:** Classroom Teaching + GitHub Repository Notes

---

## 📌 Learning Objectives

After completing this lecture, students will be able to:

* Understand what **access modifiers** are
* Explain the **need and importance** of access control
* Identify and use **public, private, protected, and default** modifiers
* Understand **access levels across packages and inheritance**
* Write clean, secure, and well-structured Java programs

---

## 📖 1. What are Access Modifiers?

**Access Modifiers** in Java define the **visibility (scope)** of classes, variables, methods, and constructors.

They help us to:

* Implement **Encapsulation**
* Protect data from unauthorized access
* Control program structure
* Improve security and maintainability

> 👉 In simple words: Access modifiers decide **"who can access what"** in a Java program.

---

## 🧠 2. Why Access Modifiers are Important?

| Reason               | Explanation                 |
| -------------------- | --------------------------- |
| Security             | Protect sensitive data      |
| Encapsulation        | Hide internal details       |
| Controlled Access    | Allow limited usage         |
| Code Maintainability | Better organized code       |
| Prevent Misuse       | Avoid unwanted modification |

---

## 🏗️ 3. Types of Access Modifiers in Java

Java provides **4 types of access modifiers:**

1. `public`
2. `private`
3. `protected`
4. `default` (no keyword)

---

## 🔐 4. Access Modifier Comparison Table

| Modifier  | Same Class | Same Package | Subclass (Other Package) | Other Package |
| --------- | ---------- | ------------ | ------------------------ | ------------- |
| public    | ✅          | ✅            | ✅                        | ✅             |
| protected | ✅          | ✅            | ✅                        | ❌             |
| default   | ✅          | ✅            | ❌                        | ❌             |
| private   | ✅          | ❌            | ❌                        | ❌             |

---

## 🌍 5. public Access Modifier

### ➤ Definition:

The `public` modifier allows access **from anywhere**.

### ➤ Use When:

* You want methods/classes to be **globally accessible**

### ➤ Example:

```java
public class Student {
    public String name;

    public void display() {
        System.out.println("Name: " + name);
    }
}
```

### ➤ Explanation:

* `name` and `display()` can be accessed **from any class and any package**.

---

## 🔒 6. private Access Modifier

### ➤ Definition:

The `private` modifier allows access **only inside the same class**.

### ➤ Use When:

* You want to **hide data**
* To implement **Data Hiding & Encapsulation**

### ➤ Example:

```java
class Account {
    private double balance;

    public void setBalance(double b) {
        balance = b;
    }

    public double getBalance() {
        return balance;
    }
}
```

### ❌ Example: Trying to Access `private` Variable from Another Class

```java
class Test {
    public static void main(String[] args) {
        Account a = new Account();
        a.balance = 5000;   // ❌ Compile-time Error
    }
}
```

### 🔴 Error Message (Typical):

```
balance has private access in Account
```

### 🔴 Error Explanation:

`balance` is **private**, so it **cannot be accessed outside the same class**. Access is allowed only using **getter and setter methods**.

### ➤ Explanation:

* `balance` cannot be accessed directly
* Accessed using **getter and setter methods**

---

## 🛡️ 7. protected Access Modifier

### ➤ Definition:

The `protected` modifier allows access:

* Within the same package
* In subclasses of other packages

### ➤ Example:

```java
class Parent {
    protected int money = 5000;
}

class Child extends Parent {
    void show() {
        System.out.println(money);
    }
}
```

### ❌ Example: Trying to Access `protected` Member from Non-Subclass (Different Package)

```java
// File: pkg1/Parent.java
package pkg1;

public class Parent {
    protected int money = 5000;
}
```

```java
// File: pkg2/Test.java
package pkg2;
import pkg1.Parent;

class Test {
    public static void main(String[] args) {
        Parent p = new Parent();
        System.out.println(p.money);   // ❌ Compile-time Error
    }
}
```

### 🔴 Error Explanation:

`money` is **protected**, and `Test` is **not a subclass**, so access is **not allowed outside the package**.

---

## 📦 8. Default Access Modifier (No Keyword)

### ➤ Definition:

When **no modifier** is specified → it is **default access**

### ➤ Scope:

* Accessible **only within same package**

### ➤ Example:

```java
class Demo {
    int x = 10;
}
```

---

## 🔐 9. Encapsulation Using Access Modifiers

### ➤ Concept:

Encapsulation = Data Hiding + Controlled Access

### ➤ Steps:

1. Make variables **private**
2. Provide **public getter and setter methods**

### ➤ Example:

```java
class Student {
    private int roll;

    public void setRoll(int r) {
        roll = r;
    }

    public int getRoll() {
        return roll;
    }
}
```

---

## 🧪 10. Real-Time Example: Bank System

```java
class BankAccount {
    private double balance;

    public void deposit(double amount) {
        balance += amount;
    }

    public double getBalance() {
        return balance;
    }
}
```

### ➤ Why private?

* Prevent illegal access to balance
* Only controlled methods can modify it

---

## 🎯 11. Interview Important Points

* Most secure modifier → `private`
* Most accessible modifier → `public`
* Used in inheritance → `protected`
* Package based → `default`

---

## ❓ 12. Viva / Oral Questions

1. What are access modifiers?
2. Why private is used?
3. Difference between protected and default?
4. Can we apply private to class? (No – only inner class)
5. Which modifier is used for data hiding?

---

## 📝 13. Practice Assignment

### Task 1: Create a `Student` class

* private variables: id, name
* public getters and setters
* display method

### Task 2: Create a `BankAccount` system

* private balance
* deposit() and withdraw() methods

---

## 🧠 14. MCQ Quiz (For Kahoot / Menti)

1. Which modifier provides highest security?

   * a) public
   * b) private
   * c) protected
   * d) default

2. Which modifier allows access in subclass of another package?

   * a) public
   * b) private
   * c) protected
   * d) default

3. Which modifier is used if nothing is specified?

   * a) public
   * b) protected
   * c) private
   * d) default

---

## 🚀 15. Mini Project Task

### Project: Secure Student Management System

* Create Student class
* Use private variables
* Use getters & setters
* Display student data

---

## 📚 16. Summary

* Access modifiers control **visibility and security**
* There are **4 types**
* Used for **Encapsulation and Data Protection**

---

## 📌 17. GitHub Repo Suggested Structure

```
java-oop-access-modifiers/
│
├── README.md
├── PublicDemo.java
├── PrivateDemo.java
├── ProtectedDemo.java
├── DefaultDemo.java
├── EncapsulationExample.java
```

---

---
Here is the **complete working Java code with `main()` function** for both cases:

---

# ✅ 1. private Access Modifier – Full Working Example with Error

### File: `Account.java`

```java
class Account {
    private double balance;

    public void setBalance(double b) {
        balance = b;
    }

    public double getBalance() {
        return balance;
    }
}
```

### File: `TestPrivate.java`

```java
public class TestPrivate {
    public static void main(String[] args) {

        Account a = new Account();

        // ❌ Direct access - NOT allowed
        // a.balance = 5000;   // Compile-time error

        // ✅ Correct way using setter
        a.setBalance(5000);

        // ✅ Access using getter
        System.out.println("Balance: " + a.getBalance());
    }
}
```

### 🔴 Compile-time Error (If you uncomment):

```
balance has private access in Account
```

### ✅ Output:

```
Balance: 5000.0
```

---

# ✅ 2. protected Access Modifier – Same Package (Working)

### File: `ProtectedDemo.java`

```java
class Parent {
    protected int money = 5000;
}

class Child extends Parent {
    void show() {
        System.out.println("Money: " + money);
    }
}

public class ProtectedDemo {
    public static void main(String[] args) {
        Child c = new Child();
        c.show();
    }
}
```

### ✅ Output:

```
Money: 5000
```

---

# ❌ 3. protected Access – Different Package (Compile-Time Error)

### File: `pkg1/Parent.java`

```java
package pkg1;

public class Parent {
    protected int money = 5000;
}
```

### File: `pkg2/TestProtected.java`

```java
package pkg2;

import pkg1.Parent;

public class TestProtected {
    public static void main(String[] args) {
        Parent p = new Parent();
        System.out.println(p.money);   // ❌ ERROR
    }
}
```

### 🔴 Compile-time Error:

```
money has protected access in Parent
```

---

# ✅ 4. protected Access – Subclass in Different Package (Working)

### File: `pkg1/Parent.java`

```java
package pkg1;

public class Parent {
    protected int money = 5000;
}
```

### File: `pkg2/Child.java`

```java
package pkg2;

import pkg1.Parent;

public class Child extends Parent {
    public static void main(String[] args) {
        Child c = new Child();
        System.out.println("Money: " + c.money);  // ✅ Allowed
    }
}
```

### ✅ Output:

```
Money: 5000
```

---

# 🎯 Best Teaching Tip

Show students **both working & error programs** — this gives **strong conceptual clarity** 💡

---

If you want, I can also give:

✅ **default access error program**
✅ **public modifier demo**
✅ **Combined all-in-one practical lab file**
✅ **Student practice sheet PDF style**

Just tell me 😄


