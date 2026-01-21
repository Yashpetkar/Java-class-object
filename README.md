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

