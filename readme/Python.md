🐍 Python — Complete Beginner to Advanced Developer Course

This course covers everything from basic syntax to OOP, modules, APIs, file handling, databases, Flask/Django, and real projects.

📌 Table of Contents

Introduction to Python

Install Python

Running Python Files

Variables & Data Types

Operators

Input & Output

Strings

Lists

Tuples

Sets

Dictionaries

Conditional Statements

Loops

Functions

Lambda Functions

Modules & Packages

File Handling

Error Handling

Object-Oriented Programming

Python Libraries

Virtual Environment

Python + MySQL / MongoDB

Python REST API (Flask)

Python Web App (Django)

Mini Projects

Final Advanced Projects

1️⃣ What is Python?

High-level, easy-to-learn programming language

Excellent for:
✔ Web development
✔ Automation
✔ Machine learning
✔ APIs
✔ Data analysis
✔ Scripting

2️⃣ Install Python

Download from: https://python.org

Check version:

python --version

3️⃣ Run Python Files
Run script:
python app.py

Run interpreter:
python

4️⃣ Variables & Data Types
name = "Jusair"
age = 20
height = 5.9
is_student = True

5️⃣ Operators
Arithmetic
a = 10 + 5
b = 10 * 2

Comparison
10 > 5
10 == 10

6️⃣ Input & Output
name = input("Enter name: ")
print("Hello", name)

7️⃣ Strings
text = "hello world"
print(text.upper())
print(text[0:5])

8️⃣ Lists
fruits = ["apple", "banana", "mango"]
fruits.append("orange")

9️⃣ Tuples

Immutable:

colors = ("red", "blue", "green")

🔟 Sets
s = {1,2,3,3}
print(s)  # duplicates removed

1️⃣1️⃣ Dictionaries
user = {
  "name": "Alex",
  "age": 25
}
print(user["name"])

1️⃣2️⃣ If/Else
age = 18
if age >= 18:
    print("Adult")
else:
    print("Minor")

1️⃣3️⃣ Loops
For Loop
for x in range(5):
    print(x)

While Loop
i = 0
while i < 5:
    print(i)
    i += 1

1️⃣4️⃣ Functions
def add(a, b):
    return a + b

print(add(5, 2))

1️⃣5️⃣ Lambda Functions
square = lambda x: x*x
print(square(4))

1️⃣6️⃣ Modules & Packages
import math
print(math.sqrt(25))


Create your own module:

# tools.py
def greet():
    print("Hello")


Use it:

from tools import greet
greet()

1️⃣7️⃣ File Handling
f = open("data.txt", "w")
f.write("Hello world")
f.close()


Read file:

with open("data.txt", "r") as f:
    print(f.read())

1️⃣8️⃣ Error Handling
try:
    x = 1 / 0
except Exception as e:
    print("Error:", e)

1️⃣9️⃣ Object-Oriented Programming (OOP)
class Person:
    def __init__(self, name):
        self.name = name
    
    def say_hello(self):
        print("Hello", self.name)

p = Person("Jusair")
p.say_hello()

2️⃣0️⃣ Popular Python Libraries
Category	Library
Data	numpy, pandas
ML	scikit-learn, tensorflow
Web	flask, django
Automation	selenium, pyautogui
API	requests
Database	pymongo, mysql-connector
2️⃣1️⃣ Virtual Environment
python -m venv env
source env/bin/activate  # Mac
env\Scripts\activate     # Windows

2️⃣2️⃣ Python + MySQL

Install:

pip install mysql-connector-python


Connect:

import mysql.connector

db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="testdb"
)

2️⃣3️⃣ Python REST API (Flask)

Install:

pip install flask


Create API:

from flask import Flask, jsonify

app = Flask(__name__)

@app.get("/")
def home():
    return jsonify({"message": "API OK"})

app.run()

2️⃣4️⃣ Python Web App (Django)

Install:

pip install django
django-admin startproject mysite


Run:

python manage.py runserver
