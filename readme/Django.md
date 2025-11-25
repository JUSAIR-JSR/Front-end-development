🐍✨ Django — Full Beginner to Advanced Developer Course

(Complete README for GitHub)

📌 Table of Contents

What is Django?

Install Django

Create Django Project

Django Project Structure

Run the Server

Create an App

URL Routing

Django Views

HTML Templates

Template Tags

Static Files

Models

Django ORM

Admin Panel

Forms

CRUD Operations

Django Authentication

Messages Framework

File Upload

Django REST Framework

Django + MySQL / PostgreSQL

Django Project Structure (Best Practice)

Mini Projects

Final Advanced Projects

1️⃣ What is Django?

Django is a Python-based web framework used to build:

✔ Websites
✔ APIs
✔ Dashboards
✔ Authentication systems
✔ Admin panels
✔ Full-stack applications

It is:

Secure

Scalable

Fast

SEO-friendly

Batteries-included (comes with authentication, ORM, admin panel)

2️⃣ Install Django
pip install django


Check version:

django-admin --version

3️⃣ Create Django Project
django-admin startproject mysite


Move into folder:

cd mysite

4️⃣ Django Project Structure
mysite/
 ├── mysite/
 │    ├── settings.py
 │    ├── urls.py
 │    ├── wsgi.py
 │    └── asgi.py
 └── manage.py

5️⃣ Run Development Server
python manage.py runserver


Visit:
👉 http://127.0.0.1:8000

6️⃣ Create a Django App
python manage.py startapp home


Add the app in settings.py:

INSTALLED_APPS = [
    ...,
    'home',
]

7️⃣ URL Routing
mysite/urls.py
from django.contrib import admin
from django.urls import path
from home import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.index),
]

8️⃣ Django Views
home/views.py
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello Django!")

9️⃣ Templates (HTML Pages)

Create folder:

home/
 └── templates/
      └── index.html

views.py
from django.shortcuts import render

def index(request):
    return render(request, "index.html")

index.html
<h1>Hello Django Template</h1>

🔟 Template Tags
Output variable:
{{ name }}

For loop:
{% for item in items %}
  <p>{{ item }}</p>
{% endfor %}

If:
{% if age > 18 %}
  <p>Adult</p>
{% endif %}

1️⃣1️⃣ Static Files (CSS / JS / Images)

Create folder:

home/
 └── static/
       └── style.css


In settings.py:

STATIC_URL = '/static/'


In HTML:

{% load static %}
<link rel="stylesheet" href="{% static 'style.css' %}">

1️⃣2️⃣ Models
models.py
from django.db import models

class Student(models.Model):
    name = models.CharField(max_length=100)
    email = models.EmailField()
    age = models.IntegerField()

1️⃣3️⃣ Django ORM

Create table:

python manage.py makemigrations
python manage.py migrate


Insert:

Student.objects.create(name="John", age=20, email="john@gmail.com")


Get all:

Student.objects.all()


Filter:

Student.objects.filter(age=20)


Update:

student.age = 25
student.save()


Delete:

student.delete()

1️⃣4️⃣ Admin Panel

Create admin user:

python manage.py createsuperuser


Register model:

from django.contrib import admin
from .models import Student

admin.site.register(Student)


Visit:
👉 http://127.0.0.1:8000/admin

1️⃣5️⃣ Django Forms
forms.py
from django import forms

class ContactForm(forms.Form):
    name = forms.CharField()
    email = forms.EmailField()

views.py
form = ContactForm()
return render(request, "contact.html", {"form": form})

auto-render:
{{ form.as_p }}

1️⃣6️⃣ CRUD Operations

✔ Create
✔ Read
✔ Update
✔ Delete

Example:

Create:
Student.objects.create(name="A", age=10)

Read:
Student.objects.all()

Update:
s = Student.objects.get(id=1)
s.age = 30
s.save()

Delete:
s.delete()

1️⃣7️⃣ Django Authentication System
Signup, Login, Logout

Built-in tools exist.

from django.contrib.auth import authenticate, login, logout

Login example:
user = authenticate(username="admin", password="123")
if user:
    login(request, user)

1️⃣8️⃣ Messages Framework
from django.contrib import messages
messages.success(request, "Login Successful")


HTML:

{% for msg in messages %}
  <p>{{ msg }}</p>
{% endfor %}

1️⃣9️⃣ File Upload
models.py
image = models.ImageField(upload_to="uploads/")

settings.py
MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / "media"

urls.py
urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

2️⃣0️⃣ Django REST Framework (DRF)

Install:

pip install djangorestframework


Add to settings:

INSTALLED_APPS += ['rest_framework']

Serializer
from rest_framework import serializers
from .models import Student

class StudentSerializer(serializers.ModelSerializer):
    class Meta:
        model = Student
        fields = '__all__'

API View
from rest_framework.response import Response
from rest_framework.decorators import api_view

@api_view(['GET'])
def all_students(request):
    students = Student.objects.all()
    return Response(StudentSerializer(students, many=True).data)

2️⃣1️⃣ Django + MySQL

Install:

pip install mysqlclient


settings.py:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'testdb',
        'USER': 'root',
        'PASSWORD': '',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}

2️⃣2️⃣ Django Project Structure (Best Practice)
project/
 ├── core/
 │     ├── settings.py
 │     ├── urls.py
 │     ├── wsgi.py
 ├── apps/
 │     └── users/
 │     └── blog/
 │     └── api/
 ├── templates/
 ├── static/
 └── manage.py
