📘 Java Course — Beginner to Advanced (2025 Edition)

Complete Java language + OOP + Collections + File Handling + Multithreading + JDBC + Mini Projects

📚 Table of Contents
Java Basics

What is Java?

Install Java (JDK)

First Java Program

Variables & Data Types

Operators

Input / Output

Conditional Statements

Loops

Core Java

Arrays

Strings

Methods

Method Overloading

OOP Concepts

Classes & Objects

Constructors

Inheritance

Polymorphism

Abstraction

Interfaces

Encapsulation

Java Advanced

Packages

Access Modifiers

Static & Final Keyword

Inner Classes

Exception Handling

File Handling

Collections Framework

Generics

Multithreading

Synchronization

JDBC + MySQL

Java Projects

Simple Calculator (OOP)

Student Management System

Library Management (File-based)

Banking System (OOP + File Storage)

Login System with File Storage

🟦 1. What is Java?

Java is a high-level, object-oriented, platform-independent programming language.

Write once, run anywhere

Used for Android, Desktop, Web, Backend, Cloud, and Banking systems

🟦 2. Install Java (JDK)

Download JDK:
https://www.oracle.com/java/technologies/downloads/

Check version:

java -version

🟦 3. First Java Program

📄 Create a file: Main.java

class Main {
    public static void main(String[] args) {
        System.out.println("Hello Java!");
    }
}


Run:

javac Main.java
java Main

🟦 4. Variables & Data Types
int age = 20;
double price = 99.5;
char grade = 'A';
String name = "Jusair";
boolean isActive = true;

🟦 5. Operators
+  -  *  /  %  
== != > < >=  
&& || !

🟦 6. Input from User
import java.util.*;

class Main {
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String name = sc.nextLine();
        System.out.println("Hello " + name);
    }
}

🟦 7. Conditions
int age = 18;

if(age >= 18){
    System.out.println("Adult");
} else {
    System.out.println("Minor");
}

🟦 8. Loops
For loop
for(int i=1; i<=5; i++){
    System.out.println(i);
}

While loop
int i=1;
while(i<=5){
    System.out.println(i);
    i++;
}

🟦 9. Arrays
int[] nums = {10, 20, 30};
System.out.println(nums[1]); // 20

🟦 10. Strings
String name = "Jusair";
System.out.println(name.length());
System.out.println(name.toUpperCase());

🟦 11. Methods
static int add(int a, int b){
    return a + b;
}

🟦 12. Method Overloading
void show(int a){}
void show(String b){}

🟦 13 – 20. OOP Concepts
Class & Object
class Student {
    String name;
    int age;

    void display(){
        System.out.println(name + " " + age);
    }
}

class Main {
    public static void main(String[] args){
        Student s = new Student();
        s.name = "Ali";
        s.age = 21;
        s.display();
    }
}

Constructor
class Person {
    Person(){
        System.out.println("Constructor called!");
    }
}

Inheritance
class A { void hello(){ System.out.println("Hello"); } }
class B extends A {}

Polymorphism
class A { void show(){ System.out.println("A show"); } }
class B extends A { void show(){ System.out.println("B show"); } }

Abstraction
abstract class Animal {
  abstract void sound();
}

class Dog extends Animal {
  void sound(){ System.out.println("Bark"); }
}

Interface
interface Car {
    void drive();
}

class BMW implements Car {
    public void drive(){
        System.out.println("Driving BMW");
    }
}

Encapsulation
class Bank {
  private double balance = 0;
  public double getBalance(){ return balance; }
}

🟦 21. Packages
package myapp;

🟦 22. Access Modifiers
Modifier	Access
public	everywhere
private	only inside class
protected	inheritance only
default	same package
🟦 23. Static & Final
static int count = 0;
final int MAX = 100;

🟦 24. Inner Classes
class Outer {
  class Inner {
    void show(){ System.out.println("Inner"); }
  }
}

🟦 25. Exception Handling
try{
   int a = 10/0;
}
catch(Exception e){
   System.out.println("Error: " + e);
}

🟦 26. File Handling
Write File
FileWriter fw = new FileWriter("data.txt");
fw.write("Hello");
fw.close();

Read File
Scanner sc = new Scanner(new File("data.txt"));
while(sc.hasNextLine()){
    System.out.println(sc.nextLine());
}

🟦 27. Collections Framework
ArrayList
ArrayList<String> list = new ArrayList<>();
list.add("A");
list.add("B");

HashMap
HashMap<String, Integer> map = new HashMap<>();
map.put("age", 20);

🟦 28. Generics
class Box<T>{
    T value;
}

🟦 29. Multithreading
class MyThread extends Thread {
  public void run(){
    for(int i=1;i<=5;i++) System.out.println(i);
  }
}

🟦 30. Synchronization
synchronized void print(){
  // thread-safe
}

🟦 31. JDBC + MySQL
Class.forName("com.mysql.cj.jdbc.Driver");
Connection con = DriverManager.getConnection(
  "jdbc:mysql://localhost:3306/db", "root", ""
);

🟦 32–36. Java Mini Projects
Student Management System (ArrayList + OOP)

CRUD operations: Add, update, delete, search

Library Management System (File Handling)

Add books, issue books, return books

Banking System (OOP + File Storage)

Deposit, withdraw, check balance

Login System (File based)

Register users & validate login

Calculator App (OOP)

Add, subtract, multiply, divide.