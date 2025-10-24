

Django is a high-level, open-source web framework written in Python. It is designed to make web development faster, simpler, and more secure by promoting rapid development and clean, reusable code.



Django follows the MVT (Model–View–Template) architecture, which is a variation of the MVC (Model–View–Controller) pattern.



Model: Handles the data and database structure.



View: Manages the logic and controls how data is displayed or processed.



Template: Represents the front-end or user interface of the web application.



Django provides many built-in features such as an admin panel, ORM (Object Relational Mapper), and security tools, helping developers create powerful web applications quickly and efficiently.



In summary, Django was built to help developers build secure, maintainable, and dynamic websites faster



&nbsp;				**features of Django** 



Open Source – Django is free and supported by a large developer community.



MVT Architecture – Follows the Model–View–Template pattern for organized and clean development.



ORM (Object Relational Mapper) – Lets you interact with databases using Python instead of SQL.



Built-in Admin Interface – Automatically provides an admin panel to manage data.



Security – Protects against common web attacks like SQL injection, XSS, and CSRF.



Scalability – Can handle both small projects and large-scale applications.



Rapid Development – Helps build and deploy applications quickly with less code.



Template System – Simplifies creating dynamic and reusable web pages.



URL Routing – Provides a clean and flexible way to manage URLs.



Extensive Libraries – Includes tools for authentication, sessions, forms, and more.



File Handling – Supports uploading, storing, and serving files such as images, documents, and media using FileField and ImageField.



Caching System – Improves performance by storing frequently used data temporarily, reducing database load.



Internationalization (i18n) – Supports multiple languages and localization.



Testing Framework – Comes with built-in tools for unit testing.



Middleware Support – Lets you process requests and responses globally.



Signals – Allows components to communicate when certain actions occur (like saving data).



Session Management – Stores user data between requests for personalized experiences.



Email Handling – Provides simple functions to send and manage emails.







&nbsp;			**advantage of Django**



Fast Development – Django’s structure and built-in tools help developers build web apps quickly.



Security – It has strong protection against common web attacks like SQL injection, XSS, and CSRF.



Scalable – Suitable for small projects and large, high-traffic websites.



Versatile – Can be used for all kinds of websites — from blogs to e-commerce and social networks.



Built-in Admin Panel – Auto-generates a powerful backend interface to manage data easily.



Reusable Code (DRY Principle) – Encourages “Don’t Repeat Yourself,” making code clean and efficient.



Large Community Support – Has rich documentation and a big developer community.



Cross-Platform – Works on Windows, macOS, and Linux.



Built-in Features – Comes with tools for authentication, caching, sessions, and file handling.



High Performance – Its caching system and efficient ORM improve speed and performance.







**\_\_init\_\_.py**



This file makes a folder behave like a Python package.



It appears automatically when you create a new Django app.



It can also be used to initialize package-level variables or import modules when the app loads.



**admin.py**



This file is used to register your models with the Django admin interface.



Once a model is registered here, you can manage its data (add, edit, delete) easily through Django’s built-in admin panel.



**Example:**



\# admin.py

from django.contrib import admin

from .models import Post



admin.site.register(Post)







🧠 **1. manage.py**



Command-line utility for managing the Django project.



Used for running the server, migrations, creating apps, etc.



**Example:**



python manage.py runserver

python manage.py makemigrations



⚙️ **2. settings.py**



Stores project configuration — like database, templates, static files, installed apps, and middleware.



**Example:**



INSTALLED\_APPS = \[

&nbsp;   'django.contrib.admin',

&nbsp;   'django.contrib.auth',

&nbsp;   'appname',

]



STATIC\_URL = '/static/'

MEDIA\_URL = '/media/'

MEDIA\_ROOT = BASE\_DIR / 'media'



🌐 **3. urls.py**



Maps URLs to views (controls navigation between pages).



**Example:**



from django.urls import path

from . import views



urlpatterns = \[

&nbsp;   path('', views.home, name='home'),

]



💡 **4. views.py**



Contains the logic for handling requests and returning responses.



**Example:**



from django.shortcuts import render



def home(request):

&nbsp;   return render(request, 'home.html')



🧱 **5. models.py**



Defines the data structure (database tables) using Python classes.



Each model maps to a table in the database.



**Example:**



from django.db import models



class Student(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   age = models.IntegerField()



🧩 **6. admin.py**



Registers models to appear in the Django admin interface.



**Example:**



from django.contrib import admin

from .models import Student



admin.site.register(Student)



⚙️ **7. apps.py**



Stores app configuration (like app name and label).



Automatically created when a new app is made.



**Example:**



from django.apps import AppConfig



class SchoolAppConfig(AppConfig):

&nbsp;   name = 'school\_app'



**🧪 8. tests.py**



Used to write automated tests for verifying app functionality.



**Example:**



from django.test import TestCase

from .models import Student



class StudentTest(TestCase):

&nbsp;   def test\_student\_creation(self):

&nbsp;       s = Student.objects.create(name="John", age=20)

&nbsp;       self.assertEqual(s.name, "John")



🧱 **9. migrations/ Folder**



Stores migration files that record model changes.



Keeps the database structure up to date.



**Example commands:**



python manage.py makemigrations

python manage.py migrate



📦 **10. \_\_init\_\_.py**



Marks the folder as a Python package, allowing imports between files.



🎨 **11. templates/ Folder**



Contains HTML files used for the front-end of the website.



Works with Django’s templating engine.



**Example (home.html):**



<!DOCTYPE html>

<html>

<head>

&nbsp;   <title>Home</title>

&nbsp;   {% load static %}

&nbsp;   <link rel="stylesheet" href="{% static 'css/style.css' %}">

</head>

<body>

&nbsp;   <h1>Welcome to Django!</h1>

</body>

</html>



💅 **12. static/ Folder**



Holds static files like CSS, JavaScript, and images.



These do not change during runtime.



**Example (style.css):**



body {

&nbsp; background-color: #f0f0f0;

&nbsp; font-family: Arial;

}





In settings.py:



STATIC\_URL = '/static/'

STATICFILES\_DIRS = \[BASE\_DIR / "static"]





In HTML:



{% load static %}

<link rel="stylesheet" href="{% static 'css/style.css' %}">



🖼️ **13. media/ Folder**



Used for user-uploaded files (like images, documents, etc.).



Works together with Django’s file handling system.



In settings.py:



MEDIA\_URL = '/media/'

MEDIA\_ROOT = BASE\_DIR / 'media'





In models.py:



class Profile(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   photo = models.ImageField(upload\_to='uploads/')



⚡ **14. asgi.py and wsgi.py**



Entry points for serving your app on web servers.



wsgi.py → used for traditional web servers.



asgi.py → supports asynchronous applications.



✅ **Summary Table**



**File / Folder	Purpose**



manage.py	Manages the Django project via command line

settings.py	Contains all configuration settings

urls.py	Maps URLs to views

views.py	Handles request and response logic

models.py	Defines database structure

admin.py	Registers models in the admin panel

apps.py	App configuration file

tests.py	For writing and running test cases

migrations/	Tracks database changes

\_\_init\_\_.py	Marks directory as a Python package

templates/	Contains HTML templates for front-end

static/	Holds CSS, JS, and image files

media/	Stores uploaded user files

asgi.py / wsgi.py	Used for web server communication





&nbsp;					**MVC**



MVC is a software design pattern used to separate an application into three main components — Model, View, and Controller.

It helps organize code, making it easier to develop, test, and maintain web applications.



**1. Model**



Represents the data and the business logic of the application.



It interacts directly with the database (for storing, retrieving, and updating data).



Example: a User or Product model that defines fields and data rules.



**2. View**



Controls the presentation layer (what the user sees).



Displays data from the Model in a user-friendly format, usually as HTML or other UI templates.



Example: an HTML page showing a list of users.



**3. Controller**



Acts as a bridge between the Model and the View.



It receives user input, processes it (with help from the Model), and sends the output to the View.



Example: a function that takes user input from a form, saves it in the database, and reloads the page.







**Advantages of MVC**



Separation of Concerns – Each component has its own responsibility.



Easier Maintenance – You can update one part without affecting others.



Reusability – Models and views can be reused across the project.



Scalability – Makes large applications easier to manage.







**In Django**



Django follows a similar pattern called MVT (Model–View–Template) —



Model → same as MVC’s Model



Template → replaces View (handles presentation)



View → acts like Controller (handles logic and connects Model + Template)







**Django MVT (Model–View–Template) Architecture**



			**MVT**





MVT is a software design pattern used by Django — it’s similar to MVC (Model–View–Controller) but with a few differences.

It separates an application into three main components to make development faster, cleaner, and easier to maintain.



**1. Model**



The Model handles everything related to the database.



It defines the data structure, the fields, and the relationships between data.



Django’s Object Relational Mapper (ORM) allows interaction with the database using Python instead of SQL.



**2. View**



The View acts as the business logic layer.



It receives requests from the user, processes data through the Model, and returns a response.



Views control what data is shown and how it is displayed using Templates.



**3. Template**



The Template is the presentation layer, which controls what the user sees.



It uses HTML and Django Template Language (DTL) to dynamically display data sent from the View.





**How MVT Works**



**User → View → Model → Database → View → Template → User**





The user sends a request.



The View processes it and communicates with the Model.



The Template presents the data to the user in a web page.





**Advantages of MVT**



Separation of Concerns – Each component handles a specific role.



Faster Development – Django automates many tasks using its ORM and built-in features.



Easy Maintenance – You can update one part without affecting others.



Reusability – Models, templates, and views can be reused in different projects.



Built-in Admin Interface – Django automatically provides an admin dashboard from defined models.







**Request–Response Cycle in Django**



The Request–Response Cycle describes how Django processes a client’s request and returns a response.

It begins when a user (client) interacts with the application (e.g., by entering a URL or submitting a form) and ends when Django sends back a response (e.g., an HTML page).



**Step-by-Step Flow**



**Client (Browser)**



The process starts when the client (user) sends a request to access a web page.



**Example:** typing a URL like https://example.com/home/ or clicking a link.





**Web Server**



The request first reaches the web server (e.g., Apache, Nginx).



The server passes the request to Django through WSGI (Web Server Gateway Interface) or ASGI (Asynchronous Server Gateway Interface).





**WSGI / ASGI Layer**



This layer acts as a bridge between the web server and the Django application.



It forwards the client’s request to Django for processing.





**URL Dispatcher (urls.py)**



Django checks the URLconf file to find a URL pattern that matches the requested path.



Once matched, it sends the request to the corresponding view function.





**View**



The View function handles the request’s logic.



It may interact with the Model to fetch or modify data, and then pass that data to a Template for presentation.





**Model**



The Model communicates with the database to perform operations such as retrieving, creating, updating, or deleting data.



It returns the data to the View.



**Template**



The Template takes the data from the View and generates an HTML page (or another format) to send back to the client.



**Response**



The View returns the rendered content wrapped in an HttpResponse object.



The WSGI/ASGI layer sends this response back to the web server.



**Client (Browser)**



Finally, the browser receives and displays the response page to the user.





**Middleware** is a layer between the request and response that allows you to process data globally before

it reaches the view (on the way in) or before it goes back to the client (on the way out).

Think of middleware as a pipeline — every request passes through it before reaching the view, and 

every response passes through it before being sent to the user.


A flowchart (sometimes spelled flow chat by mistake) is a diagram that shows the steps in a process using different shapes and arrows.

It’s like a visual map that helps you understand how something works — step by step.


A PRD is a detailed document that explains what a product or feature should do and why it’s being built.
It’s like a blueprint or plan for developers, designers, and stakeholders.


from django.utils import timezone is used to import timezone in django


pk means primary key treats the post as a singular entity 









