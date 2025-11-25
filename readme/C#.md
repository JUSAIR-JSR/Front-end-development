📘 C# Complete Course (Beginner to Advanced)

Perfect for learning C# for console apps, desktop apps, Unity GameDev, backend APIs (.NET), and interviews.

⭐ 1. Introduction to C#
What is C#?

C# (C-Sharp) is a modern, object-oriented programming language.

Developed by Microsoft.

Runs on .NET framework / .NET Core.

Used for:

Desktop apps (Windows Forms, WPF)

Web APIs

Unity game development

Mobile apps (Xamarin, MAUI)

Enterprise applications

⭐ 2. Install & Setup
Step 1 — Install .NET SDK

Download: https://dotnet.microsoft.com/download

Step 2 — Check installation
dotnet --version

Step 3 — Create a new C# project
dotnet new console -o MyApp
cd MyApp

Step 4 — Run the project
dotnet run

⭐ 3. Basic Syntax
Hello World
using System;

class Program {
    static void Main() {
        Console.WriteLine("Hello World");
    }
}

⭐ 4. Variables
string name = "Jusair";
int age = 20;
double height = 5.8;
bool isStudent = true;

Data Types:
Type	Example
int	10
float	2.4f
double	3.99
bool	true/false
char	'A'
string	"Hello"
⭐ 5. Input from User
Console.Write("Enter your name: ");
string name = Console.ReadLine();

Console.WriteLine("Hello " + name);

⭐ 6. Operators
Arithmetic
+, -, *, /, %

Comparison
==, !=, >, <, >=, <=

Logical
&&, ||, !

⭐ 7. Conditional Statements
If / Else
int age = 18;

if(age >= 18) {
    Console.WriteLine("Adult");
} else {
    Console.WriteLine("Minor");
}

Switch
int day = 3;

switch(day) {
    case 1: Console.WriteLine("Monday"); break;
    case 2: Console.WriteLine("Tuesday"); break;
    default: Console.WriteLine("Other day"); break;
}

⭐ 8. Loops
For loop
for(int i=1; i<=5; i++) {
    Console.WriteLine(i);
}

While loop
int i = 1;
while(i <= 5) {
    Console.WriteLine(i);
    i++;
}

Foreach
string[] fruits = { "Apple", "Mango", "Banana" };

foreach(string f in fruits) {
    Console.WriteLine(f);
}

⭐ 9. Arrays
int[] numbers = { 10, 20, 30 };

Console.WriteLine(numbers[1]);  // 20

⭐ 10. Methods / Functions
static void Greet(string name) {
    Console.WriteLine("Hello " + name);
}

static void Main() {
    Greet("Jusair");
}

⭐ 11. Object-Oriented Programming (OOP)
Class & Object
class Person {
    public string Name;
    public int Age;

    public void Speak() {
        Console.WriteLine($"{Name} is speaking.");
    }
}

class Program {
    static void Main() {
        Person p = new Person();
        p.Name = "Ali";
        p.Age = 22;
        p.Speak();
    }
}

⭐ 12. Constructor
class Car {
    public string Brand;

    public Car(string brand) {
        Brand = brand;
    }
}

var c = new Car("BMW");
Console.WriteLine(c.Brand);

⭐ 13. Inheritance
class Animal {
    public void Eat() {
        Console.WriteLine("Eating...");
    }
}

class Dog : Animal {
    public void Bark() {
        Console.WriteLine("Barking...");
    }
}

⭐ 14. Polymorphism
class Shape {
    public virtual void Draw() {
        Console.WriteLine("Drawing Shape");
    }
}

class Circle : Shape {
    public override void Draw() {
        Console.WriteLine("Drawing Circle");
    }
}

⭐ 15. Interface
interface IAnimal {
    void MakeSound();
}

class Dog : IAnimal {
    public void MakeSound() {
        Console.WriteLine("Woof!");
    }
}

⭐ 16. Exception Handling
try {
    int x = 10 / 0;
}
catch(Exception ex) {
    Console.WriteLine("Error: " + ex.Message);
}

⭐ 17. File Handling
using System.IO;

File.WriteAllText("data.txt", "Hello World");

string text = File.ReadAllText("data.txt");
Console.WriteLine(text);

⭐ 18. Async / Await
using System.Threading.Tasks;

static async Task FetchData() {
    await Task.Delay(1000);
    Console.WriteLine("Data loaded");
}

⭐ 19. Build a Mini C# Project (To-Do App)
List<string> tasks = new List<string>();

while(true) {
    Console.Write("Add task: ");
    string t = Console.ReadLine();
    tasks.Add(t);

    Console.WriteLine("\nYour Tasks:");
    foreach(string task in tasks) Console.WriteLine("- " + task);
}

⭐ 20. What Next? (Advanced Track)
After basics → Learn these:

.NET Web API

Entity Framework

LINQ

ASP.NET MVC

MAUI (Mobile)

Unity Game Development

Clean Architecture

Azure Deployment