📘 C++ Programming Course (Beginner to Advanced)

Learn C++ for DSA, competitive programming, game engines, system programming, OOP, file handling, STL, and interviews.

⭐ 1. Introduction to C++
What is C++?

C++ is a high-performance programming language.

Used for:

Game development (Unreal Engine)

Competitive coding (CP)

System-level programming

Operating systems

Banking & enterprise software

DSA and problem solving

⭐ 2. Install & Setup
Install MinGW / g++

Check version:

g++ --version

Create & Run program:
g++ program.cpp -o program
./program

⭐ 3. Basic Program
#include <iostream>
using namespace std;

int main() {
    cout << "Hello World";
    return 0;
}

⭐ 4. Variables & Data Types
int age = 20;
float height = 5.9;
double salary = 50000.55;
char grade = 'A';
string name = "Jusair";
bool isStudent = true;

⭐ 5. Input & Output
int x;
cin >> x;
cout << "Value: " << x;

⭐ 6. Operators
Arithmetic
+, -, *, /, %

Comparison
==, !=, >, <, >=, <=

Logical
&&, ||, !

⭐ 7. Conditional Statements
If / Else
if(age >= 18) cout << "Adult";
else cout << "Minor";

Switch
switch(day) {
    case 1: cout << "Mon"; break;
    default: cout << "Other";
}

⭐ 8. Loops
For
for(int i=1; i<=5; i++)
    cout << i << endl;

While
int i = 1;
while(i <= 5) {
    cout << i;
    i++;
}

Do While
int i = 1;
do {
    cout << i;
    i++;
} while(i <= 5);

⭐ 9. Arrays
int nums[3] = {10, 20, 30};
cout << nums[1]; // 20

⭐ 10. Strings
string name = "Jusair";
cout << name;

⭐ 11. Functions
void greet(string name) {
    cout << "Hello " << name;
}

int add(int a, int b) {
    return a + b;
}

⭐ 12. Object-Oriented Programming (OOP)
Class & Object
class Person {
public:
    string name;
    int age;

    void speak() {
        cout << name << " is speaking";
    }
};

int main() {
    Person p;
    p.name = "Ali";
    p.age = 21;
    p.speak();
}

⭐ 13. Constructors
class Car {
public:
    string brand;

    Car(string b) {
        brand = b;
    }
};

⭐ 14. Inheritance
class Animal {
public:
    void eat() { cout << "Eating"; }
};

class Dog : public Animal {
public:
    void bark() { cout << "Barking"; }
};

⭐ 15. Polymorphism
Function Overriding
class Shape {
public:
    virtual void draw() {
        cout << "Drawing shape";
    }
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing circle";
    }
};

⭐ 16. Abstraction
class Animal {
public:
    virtual void sound() = 0;   // Pure virtual function
};

⭐ 17. Encapsulation
class Bank {
private:
    int balance;

public:
    void setBalance(int b) { balance = b; }
    int getBalance() { return balance; }
};

⭐ 18. Pointers
int x = 10;
int *ptr = &x;

cout << *ptr;  // 10

⭐ 19. Dynamic Memory Allocation
int *p = new int;
*p = 10;
cout << *p;
delete p;

⭐ 20. File Handling
Write file
ofstream file("data.txt");
file << "Hello";
file.close();

Read file
ifstream file("data.txt");
string text;
getline(file, text);
cout << text;
file.close();

⭐ 21. STL (Standard Template Library)

One of the most powerful features in C++.

Vectors
vector<int> v = {1,2,3};
v.push_back(4);
cout << v[0];

Sets
set<int> s;
s.insert(10);
s.insert(20);

Maps
map<string, int> m;
m["age"] = 20;
cout << m["age"];

Queue
queue<int> q;
q.push(10);
q.pop();

Stack
stack<int> s;
s.push(5);
s.pop();

⭐ 22. Exception Handling
try {
    throw 10;
} catch(int e) {
    cout << "Error: " << e;
}

⭐ 23. C++ Mini Projects
➤ 1. BMI Calculator
float w, h;
cin >> w >> h;
cout << "BMI = " << w/(h*h);

➤ 2. To-Do App
vector<string> tasks;
string t;

while(true) {
    cout << "Add task: ";
    cin >> t;
    tasks.push_back(t);

    for(string x : tasks) cout << "- " << x << endl;
}

➤ 3. Student Management

Add student

Delete student

Search student

Display all students