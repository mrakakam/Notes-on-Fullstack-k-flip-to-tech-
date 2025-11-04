🎯 Topic: Django Introduction \& Features

➤ What is Django?



Django is a high-level, Python-based web framework used to build secure and scalable web applications fast.



It follows the MVT (Model-View-Template) architecture.



➤ Why Django?



Django helps developers move from idea → full web app quickly, without worrying about deep backend complexity like security, database handling, and routing.



➤ Key Features



🔹 Fast Development

Build apps quicker — lots of features already done for you.



🔹 Secure

Includes protections against common attacks (SQL injection, CSRF, XSS, etc).



🔹 Scalable

Used by big apps like Instagram \& Pinterest — can handle lots of users.



🔹 Built-in Admin Panel

Auto-generated dashboard to manage data — no extra coding (major advantage).



🔹 ORM (Object Relational Mapping)

Interact with the database using Python, not SQL queries.



🔹 MVT Architecture

Clean structure: Model → View → Template



🔹 Open-Source \& Community Support

Huge community + lots of packages.



🔹 Batteries-Included Philosophy

Django ships with everything ready:



Auth system



Admin panel



Forms



Session \& cookies



Routing system



Security features



✅ You don't need many external packages — Django gives you most tools.



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End🔚 End 🔚 End







🎯 Topic: MVC vs MVT

➤ Simple Meaning



Both are architectures used to build web applications, but Django uses MVT instead of MVC.



➤ Difference Explained Simply

✅ MVC (Model – View – Controller)



Model → Manages the data/database



View → What user sees (UI)



Controller → Handles user requests \& connects Model + View



✅ MVT (Model – View – Template) (Django)



Model → Manages the data/database (same as MVC)



View → Handles logic (fetch data, send to template)



Template → HTML files / UI



➤ Key 🔍 Point



In Django, the framework itself acts as the Controller, so you don't write a separate controller file.



You only write:



✅ Model



✅ View



✅ Template



Django handles the connection part automatically.



| Part    | File         |

| ------- | ------------ |

| Data    | `models.py`  |

| Logic   | `views.py`   |

| UI HTML | `templates/` |



Django secretly works as the controller ✅



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End🔚 End🔚 End







🎯 Topic: Django Project vs Django App

➤ Simple Explanation



Think of Django like a big house (Project) that contains many rooms (Apps).



Project = The entire website setup



App = A module/feature inside the project (like blog, users, store)



You can have one project and many apps inside it.

➤ Real-Life Example



| Real Life                      | Django                                        |

| ------------------------------ | --------------------------------------------- |

| House                          | Django Project                                |

| Rooms (Bedroom, Kitchen, etc.) | Django Apps (Blog app, Auth app, Payment app) |





➤ Key 🔍 Point



A Django project can work without many apps…



But an app always needs a project to run ✅



✅ Example



Command to create a project: django-admin startproject mysite



Command to create an app: python manage.py startapp blog(name of app )





File structure after creating project + app:👇⬇️

mysite/

&nbsp;  manage.py

&nbsp;  mysite/  ← project folder

&nbsp;  blog/ ← app folder





➤ What Each One Does



Project handles:



Settings



Database config



URL connections for all apps



App handles:



Models



Views



URLs



Templates for one feature



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End🔚 End





🎯 Topic: Django URL Routing

➤ Simple Explanation



URL routing in Django decides what page or function runs when a user visits a URL.



Think of it like a map that guides URLs to the correct view function.



Example:



\- /home → show homepage



\- /contact → show contact page



➤ Why It’s Important



Without URL routing, your website wouldn't know which code to run for each link.



✅ Example



urls.py 🛣️ (URL Route File)



from django.urls import path

from . import views



urlpatterns = \[

&nbsp;   path('home/', views.home),

]



views.py 👨‍💻 (Page Logic / Function)



from django.http import HttpResponse



def home(request):

&nbsp;   return HttpResponse("Welcome to Home Page")





Now when user visits:

http://127.0.0.1:8000/home/ → It runs home() function ✅



➤ Key 🔍 Point



urls.py 🛣️ = Decides the route



views.py 👨‍💻 = Executes the logic



Django connects:



URL 🛣️ → View 👨‍💻 → Response ✅



🔚 End  🔚 End  🔚 End  🔚 End  🔚 End  🔚 End  🔚 End 🔚 End 





🎯 Topic: Django Models \& Database

➤ Simple Explanation



In Django, Models are used to create and manage database tables 📦.



A Model = A table in your database ✅

Each attribute = A column 🧱



Example: A Customer model creates a Customer table in DB.



➤ Why It’s Important



Stores data 📁



Easy to create tables without writing SQL ❌🧠



Django handles everything automatically ✅



✅ Example



models.py 🧱 (Database Structure)

from django.db import models



class Customer(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   email = models.EmailField(unique=True)





This will create a Customer table with:



name (text field)



email (unique email field)





➤ How it works in Django



1️⃣ Write model in models.py 🧱

2️⃣ Run migrations ⚙️

3️⃣ Django creates table in database 💾



➤ Commands to Activate Model



python manage.py makemigrations

python manage.py migrate



🔍 Key Point



Model = Data Blueprint

Django = Auto builds table in DB 😎



✅ Table created without touching SQL 🎉



NOTE 📜: Structured Query Language — a special programming language used to talk to databases.



✅ Simple Meaning



SQL is how computers store, search, add, and remove data in databases.



Example SQL actions:



Create a table



Insert data



Update data



Delete data



Fetch (read) data



💡 Why we mentioned it



Django models let you work with databases without writing SQL manually.



Instead of typing SQL commands like 👇⬇️:

INSERT INTO customers (name, email) VALUES ("John", "john@gmail.com");



You just write Python 🐍:

Customer.objects.create(name="John", email="john@gmail.com")





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





Topic: 🎯 Database in Django



➤ A database stores your app data permanently (users, bookings, products, messages, etc.)



➤ Django comes with SQLite by default

Good for learning \& small/medium projects ✅



➤ For bigger systems, Django works with:



PostgreSQL 🧱 (best choice)



MySQL 💾



MariaDB 🗄️



➤ Django uses Models to create tables

➤ You don't write SQL — Django converts models → SQL automatically



✅ Example



class Student(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   age = models.IntegerField()





Django will create a Student table in the database automatically ✅



🔑 Key Point



Django = Write Python → Creates SQL tables for you



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





Topic: 🎯 Django Admin Panel



➤ Django comes with a built-in admin dashboard to manage your whole site



➤ It lets you:



Add, update, delete data ✅



Manage users 👤



Approve bookings / orders 📦



View database records without SQL 📊



➤ Super powerful for business apps like spas, e-commerce, blogs, CRM, etc 🧠



✅ Example



Create superuser (admin account):

python manage.py createsuperuser



Log in at:

http://127.0.0.1:8000/admin



Register your model to show it in admin:



from django.contrib import admin

from .models import Customer



admin.site.register(Customer)



💡 Key Point



Admin panel = free backend dashboard — no coding UI needed.



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





Topic: 🎯 Django Models



➤ Models are how Django handles database tables 🗄️

➤ They define the structure of your data (fields, types, rules)



Think of models.py as:



Blueprint for database table 🧩



Where you define columns (name, email, price, date…) 📍



✅ Example



from django.db import models



class Customer(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   email = models.EmailField(unique=True)

&nbsp;   joined\_at = models.DateTimeField(auto\_now\_add=True)



&nbsp;   def \_\_str\_\_(self):

&nbsp;       return self.name



🔑 Key Points



Every model = a database table 📂



Every field = a column 🧱



Django automatically creates SQL behind the scenes 👨‍💻



\_\_str\_\_ helps show readable names in admin 👁️



To apply model changes:



python manage.py makemigrations

python manage.py migrate





✅ Boom — database updated!



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





Topic: 🎯 Django Views



➤ Views are where your logic lives 🧠

➤ They take a request and return a response (HTML, JSON, redirect, etc)



Think of views as the brain of your app.



✅ Simple View Example

from django.http import HttpResponse



def home(request):

&nbsp;   return HttpResponse("Welcome to Bliss Haven Spa 🌿")



✅ View Rendering Template

from django.shortcuts import render



def about(request):

&nbsp;   return render(request, 'about.html')





🔥 Views Types

| Type                          | Purpose                     |

| ----------------------------- | --------------------------- |

| \*\*Function-Based View (FBV)\*\* | Simple logic 👇             |

| \*\*Class-Based View (CBV)\*\*    | Advanced, reusable logic 🧠 |





⚡ How views work in Django



Request → URL → View → Response



Example flow:



Client Browser → /about → about() view → about.html page



💡 Key Notes



Views = logic center



They connect models \& templates



Can return HTML, JSON, redirects, forms, etc



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





Topic: 🎯 Django Models



➤ Models represent data \& database tables 🗄️

➤ Every model = one table in database

➤ Written in Python, Django converts to SQL automatically ✅



✅ Example Model



from django.db import models



class Product(models.Model):

&nbsp;   name = models.CharField(max\_length=200)

&nbsp;   price = models.DecimalField(max\_digits=10, decimal\_places=2)

&nbsp;   created\_at = models.DateTimeField(auto\_now\_add=True)



🔍 Key Field Types



| Field             | Meaning                          |

| ----------------- | -------------------------------- |

| `CharField()`     | Short text (names, titles)       |

| `TextField()`     | Long text (description, content) |

| `IntegerField()`  | Whole numbers                    |

| `DecimalField()`  | Money \& decimal values 💰        |

| `BooleanField()`  | True/False values                |

| `DateTimeField()` | Time \& date                      |





⚙️ After creating a Model



Run migrations to create the table in DB:



python manage.py makemigrations

python manage.py migrate



⭐ Why Models are Important



Store data permanently ✅



Manage relationships (1–1, 1–many, many–many)



Django ORM removes need to write SQL manually



Cleaner, faster database operations



🧠 Quick Memory Tip



Model = 🧱 Blueprint for database table



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





Topic: 🎯 Django Admin Panel



➤ Django gives a built-in admin dashboard to manage your database 👑

➤ You can add, edit, and delete data without writing code ✅

➤ Very useful for beginners \& backend management tools



✅ How to Enable Admin



Make a superuser:



python manage.py createsuperuser





Enter:



Username 👤



Email 📧 (optional)



Password 🔐



Then log in at:



http://127.0.0.1:8000/admin



✅ Register Models in Admin



So they appear in the panel:



from django.contrib import admin

from .models import Product



admin.site.register(Product)





Now you can manage Product data inside admin 👏



✨ Features of Admin Panel



View \& edit database safely



Search and filter data 🔎



Auto-generated forms ✍️



Control user accounts \& permissions 🔐



⭐ Memory Tip



Admin = God-mode dashboard to control your app data 👑



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Topic: Django URLs (Beginner-Friendly Notes)



➤ What are URLs in Django?

URLs tell Django which page or function to run when a user visits a link.



Example:

/about → show about page

/contact → show contact page



➤ Why URLs are Important?

They connect the browser request to the correct view function in Django.



➤ Where do URLs go?



project/urls.py → main URL settings



app/urls.py → app-specific URLs (recommended for big projects)



➤ URL Flow

User enters website address → Django checks urls.py → calls correct view



➤ Basic URL Code Structure



✅ Example (project urls.py)



from django.contrib import admin

from django.urls import path

from myapp import views



urlpatterns = \[

&nbsp;   path('admin/', admin.site.urls),

&nbsp;   path('', views.home),  # homepage

]





✅ Example (views.py)



from django.http import HttpResponse



def home(request):

&nbsp;   return HttpResponse("Welcome to Bliss Haven Spa 🌸")





✅ Example (browser)

Go to: http://localhost:8000/ → Displays Welcome to Bliss Haven Spa 🌸



➤ Note



path() is used to create routes



Each path must call a view function



' ' empty path = homepage



➤ In simple words

URLs = map of your website

They link pages to the right logic



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Topic: Django Views (Beginner-Friendly Notes)



➤ What are Views in Django?

Views are Python functions (or classes) that handle the request and return a response (HTML, JSON, text, etc.)



Think of Views as the brain of your Django app.



➤ Why are Views Important?

They decide what the user sees when they visit a URL.



Example tasks of views:



Show a webpage ✅



Read data from a database ✅



Return API response ✅



Process a form ✅



➤ Where are Views written?

Inside views.py (in each app)



➤ Simple Flow Explanation



User visits a page → URL points to View → View sends back webpage



➤ Basic Function-Based View



✅ Example — views.py



from django.http import HttpResponse



def home(request):

&nbsp;   return HttpResponse("Hello Customer 👋 Welcome to Bliss Haven Spa ✨")





✅ In urls.py



from django.urls import path

from . import views



urlpatterns = \[

&nbsp;   path('', views.home),

]





➤ Returning HTML from views



✅ Example



from django.shortcuts import render



def services(request):

&nbsp;   return render(request, 'services.html')





➤ Notes



HttpResponse → text response



render() → sends HTML template



View decides what to do when URL is visited



➤ Simple Definition

Views = Logic + Response

They handle data \& return a page/content



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Topic: Django Templates (Beginner-Friendly Notes)



➤ What are Templates in Django?

Templates are HTML files where you display data from your views.

They help you build webpages with dynamic content (text, images, loops, username, data from DB, etc.)



Simply:

Views send data → Templates show data



➤ Where are Templates stored?

Usually inside:



app\_name/templates/





Example folder structure:



myapp/

&nbsp;└─ templates/

&nbsp;    └─ home.html





➤ Basic Example



✅ Template file (home.html)



<!DOCTYPE html>

<html>

<head>

&nbsp;   <title>Welcome</title>

</head>

<body>

&nbsp;   <h1>Hello {{ name }} 👋</h1>

</body>

</html>





✅ View sending data



from django.shortcuts import render



def home(request):

&nbsp;   return render(request, 'home.html', {'name': 'Bliss Haven Client'})





✅ Output



Hello Bliss Haven Client 👋



➤ Django Template Language (DTL) — Mini Cheat Sheet



| Purpose           | Syntax                   |

| ----------------- | ------------------------ |

| Display variable  | `{{ variable }}`         |

| If condition      | `{% if condition %}`     |

| Loop              | `{% for item in list %}` |

| Load static files | `{% load static %}`      |



➤ Loop Example



<ul>

{% for item in services %}

&nbsp; <li>{{ item }}</li>

{% endfor %}

</ul>





➤ Important Points



Templates = Only for frontend display



Use them with render() in views



They allow logic only for display (not Python code)



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Topic: Django Template Tags \& Filters



➤ What are Template Tags \& Filters?

When using templates in Django, we sometimes need logic like loops, conditions, or formatting text.

Template Tags and Filters help us do that inside HTML — without writing Python code.



➤ Template Tags (Control Logic)



Used for loops, conditions, loading static files, etc.



Common Tags:



| Purpose              | Syntax                                    |

| -------------------- | ----------------------------------------- |

| If condition         | `{% if %} ... {% endif %}`                |

| For loop             | `{% for item in list %} ... {% endfor %}` |

| Load static files    | `{% load static %}`                       |

| Template inheritance | `{% block %} / {% endblock %}`            |



✅ Example: If \& Loop



{% if services %}

&nbsp; <ul>

&nbsp; {% for s in services %}

&nbsp;   <li>{{ s }}</li>

&nbsp; {% endfor %}

&nbsp; </ul>

{% else %}

&nbsp; <p>No services available 😢</p>

{% endif %}



➤ Template Filters (Modify Data)



Filters modify values in templates.



Syntax:



{{ value|filter }}



Popular filters:



| Filter | Use     |                           |

| ------ | ------- | ------------------------- |

| `      | upper`  | Change text to uppercase  |

| `      | lower`  | Lowercase                 |

| `      | title`  | Capitalize each word      |

| `      | length` | Count items or characters |

| `      | date`   | Format date               |

| `      | safe`   | Render HTML safely        |



✅ Example:



<p>{{ name|upper }}</p>

<p>Total Services: {{ services|length }}</p>



➤ Static Files Example (Images / CSS)

{% load static %}



<img src="{% static 'images/spa.jpg' %}" alt="Spa Image">

<link rel="stylesheet" href="{% static 'css/style.css' %}">



✅ Why Use Tags \& Filters?



Add light logic without Python



Display data properly



Format text, numbers, time



Work clean \& secure



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Topic: Django Static \& Media Files



➤ What are Static \& Media Files?



Type	Meaning

Static Files	Files used by your website UI (CSS, JS, images, fonts)

Media Files	Files uploaded by users (profile pics, product images, etc.)



Django keeps them separate for better organization \& security ✅



➤ Static Files (Developer Files)



Used for styling \& front-end assets.



📌 Store in:



project/static/





📌 Must load in template:



{% load static %}

<link rel="stylesheet" href="{% static 'css/style.css' %}">

<img src="{% static 'images/logo.png' %}" alt="logo">





📌 settings.py:



STATIC\_URL = '/static/'

STATICFILES\_DIRS = \[BASE\_DIR / "static"]



➤ Media Files (User Uploaded Files)



Used for user uploads like profile photos, product images, documents.



📌 settings.py:



MEDIA\_URL = '/media/'

MEDIA\_ROOT = BASE\_DIR / 'media'





📌 urls.py:



from django.conf import settings

from django.conf.urls.static import static



urlpatterns = \[

&nbsp;  ...

] + static(settings.MEDIA\_URL, document\_root=settings.MEDIA\_ROOT)





📌 Model Example:



class Profile(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   photo = models.ImageField(upload\_to='profiles/')





📌 Template Example:



<img src="{{ user.photo.url }}" alt="Profile Picture">



✅ Real-World Use



| File               | Type   | Example           |

| ------------------ | ------ | ----------------- |

| `logo.png`         | Static | Developer uploads |

| `user\_profile.jpg` | Media  | Customer uploads  |



➤ Key Point



Static = Your assets

Media = User uploaded files



Both work together to make websites look nice + handle uploads ✅



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Topic: Django Template Language (DTL)



➤ What is Django Template Language?



Django Template Language (DTL) is Django’s system for writing dynamic HTML.



It lets you:



Show data from backend in HTML



Use loops \& conditions inside templates



Reuse layouts (extends, include)



✅ Helps you build pages that react to database/user data.



➤ Template Syntax Basics



| Feature              | Syntax           |

| -------------------- | ---------------- |

| \*\*Output variables\*\* | `{{ variable }}` |

| \*\*Tags / logic\*\*     | `{% tag %}`      |

| \*\*Comments\*\*         | `{# comment #}`  |



➤ Example: Showing a variable



✅ HTML



<p>Hello, {{ username }}</p>



➤ Example: Loop in Template

{% for item in products %}

&nbsp; <p>{{ item.name }}</p>

{% endfor %}



➤ Example: If Condition

{% if user.is\_authenticated %}

&nbsp; <p>Welcome, {{ user.username }}</p>

{% else %}

&nbsp; <p>Please log in.</p>

{% endif %}



➤ Extending Templates (Layout System)



base.html (main template)



<!DOCTYPE html>

<html>

&nbsp; <body>

&nbsp;   {% block content %}{% endblock %}

&nbsp; </body>

</html>





Child Template:



{% extends 'base.html' %}



{% block content %}

<h1>Dashboard</h1>

{% endblock %}



✅ Key Real-Life Idea



DTL is like filling content in reusable web pages, similar to WordPress themes 🧠



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Topic: Django Static Files



➤ What are Static Files?



Static files are files that do not change (not generated by Python).

Examples:



CSS 🎨



JavaScript ⚙️



Images 🖼️



Logos / Icons ⭐



Django needs a special setup to serve these during development \& production.



➤ Static Folder Structure



Inside your app:



app\_name/

&nbsp;└── static/

&nbsp;     └── app\_name/

&nbsp;         └── style.css



➤ Tell Django Where Static Files Are



In settings.py



STATIC\_URL = '/static/'



➤ Load Static in Template



First line inside HTML:



{% load static %}





Use static file:



<link rel="stylesheet" href="{% static 'app\_name/style.css' %}">

<img src="{% static 'app\_name/logo.png' %}" alt="Logo">



✅ Example



index.html



{% load static %}

<img src="{% static 'site/images/spa.png' %}" alt="Spa">

<link rel="stylesheet" href="{% static 'site/css/main.css' %}">



➤ Why Needed?



Without Django static setup, CSS/images won’t load 🚫

Django protects \& organizes your assets ✅



🧠 Memory Tip



Static files = Dress \& decoration of your website 👗✨



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Topic: Django Template Inheritance



➤ What is Template Inheritance?



Template inheritance allows you to create one main layout

and reuse it for multiple pages ✅

(so you don’t rewrite the same HTML every time)



➤ Why use it?



Avoid repeating navbar/footer/header 🔁



Faster development ⚡



Cleaner template structure 🧼



Easy to update layout ✅



➤ Base Template (base.html)

<!DOCTYPE html>

<html>

<head>

&nbsp; <title>Bliss Haven Spa</title>

</head>



<body>



&nbsp; <header>

&nbsp;   <h1>Welcome to Bliss Haven 🌿</h1>

&nbsp; </header>



&nbsp; {% block content %}{% endblock %}



&nbsp; <footer>

&nbsp;   <p>© 2025 Bliss Haven Spa</p>

&nbsp; </footer>



</body>

</html>



➤ Extend Base Template



home.html



{% extends 'base.html' %}

{% block content %}



<h2>Relax \& Refresh 💆‍♀️✨</h2>

<p>Your comfort is our priority.</p>



{% endblock %}



➤ Key Points



{% extends %} → inherit base template



{% block content %} → area where your page content appears



Base template acts like master layout



✅ Example Explanation



When you load home.html,

Django uses base.html layout and inserts the page content inside the block.



🧠 Memory Trick



Think of a template like a house plan —

every room (page) uses the same structure.



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Topic: Django Static Files (CSS, JS, Images)



➤ What are Static Files?



Static files are non-Python files used to style and add behavior to your website:



CSS 🎨



JavaScript ⚙️



Images 🖼️



Fonts 🔤



They do not change dynamically like templates.



➤ Why do we need them?



To style your Django pages 👗✨



Add interactivity ✅



Display logos, icons, pictures 📸



➤ Enable Static Files in Django



In settings.py



STATIC\_URL = '/static/'





Create a folder:



projectname/

&nbsp;└─ static/

&nbsp;    └─ css/

&nbsp;        └─ style.css



➤ Load Static in Template



At the top of your HTML template:



{% load static %}





Add your CSS file in <head>:



<link rel="stylesheet" href="{% static 'css/style.css' %}">



✅ Example



Folder:



static/images/logo.png





Use in template:



<img src="{% static 'images/logo.png' %}" alt="Spa Logo">



➤ Important Notes



static/ folder holds all front-end assets



Must load static in template using {% load static %}



In production, Django collects files using:



python manage.py collectstatic





🚀 Django then serves them efficiently



🧠 Memory Trick



Templates = dynamic pages

Static = design \& files (don’t change)



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Topic: Django Media Files (User Uploaded Files)



➤ What are Media Files?



Media files are files uploaded by users, not developers.



Examples:



Profile pictures 👤📸



Uploaded documents 📄



Product images 🛍️



Resume files 📂



They are dynamic (change based on user activity).



➤ Difference Between Static \& Media

Static Files	Media Files

Created by developer	Uploaded by user

Stored in /static/	Stored in /media/

CSS, JS, images	Profile pics, uploads

➤ Setup Media in Django



In settings.py:



MEDIA\_URL = '/media/'

MEDIA\_ROOT = BASE\_DIR / 'media'



➤ Add Media URL in urls.py



Inside project's urls.py:



from django.conf import settings

from django.conf.urls.static import static



urlpatterns = \[

&nbsp;   # your paths...

]



if settings.DEBUG:

&nbsp;   urlpatterns += static(settings.MEDIA\_URL, document\_root=settings.MEDIA\_ROOT)



✅ Example



Upload path in model:



class Profile(models.Model):

&nbsp;   photo = models.ImageField(upload\_to='profile\_pics/')





Folder structure created automatically:



media/profile\_pics/userphoto.jpg



➤ Using Media in Template



In template:



<img src="{{ user.profile.photo.url }}" alt="user photo">



🧠 Memory Trick



Static = developer files

Media = user files



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Topic: Django Template Language (DTL)



➤ What is DTL?



Django Template Language is Django’s system for writing HTML pages with Python-like logic inside them.



It helps you:



Display data from views



Loop through lists



Show conditions (if/else)



Include other templates



Avoid writing raw Python in HTML



➤ Key Template Syntax

| Purpose               | Syntax           |

| --------------------- | ---------------- |

| Output / Display data | `{{ variable }}` |

| Tags (logic)          | `{% tag %}`      |

| Comments              | `{# comment #}`  |



✅ Example: Displaying Data

<h2>Hello, {{ user.username }}</h2>



✅ Example: Loop

{% for item in products %}

&nbsp; <p>{{ item.name }}</p>

{% endfor %}



✅ Example: If Condition

{% if user.is\_authenticated %}

&nbsp; <p>Welcome, {{ user.username }}!</p>

{% else %}

&nbsp; <p>Please log in.</p>

{% endif %}



➤ Template Inheritance (Very Important)



base.html



<body>

&nbsp; {% block content %}{% endblock %}

</body>





home.html



{% extends "base.html" %}

{% block content %}

<h1>Home Page</h1>

{% endblock %}





Code reuse = easier \& cleaner ✅



🧠 Quick Tip



{{ }} = Show data

{% %} = Logic / Loops / If / Extends

{# #} = Comments



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Django REST Framework (DRF) – Beginner Notes



➤ What is DRF?



DRF = Django REST Framework



Tool for building APIs in Django (so frontend like React, mobile apps, etc. can communicate with backend)



➤ Why DRF?



Easy JSON responses



Built-in authentication



Serialization (convert DB data → JSON)



Browsable API UI



➤ Install DRF



pip install djangorestframework





➤ Add to settings



INSTALLED\_APPS = \[

&nbsp;   ...,

&nbsp;   'rest\_framework',

]





➤ Serializer (converts model ↔ JSON)

💡 Example (serializers.py):



from rest\_framework import serializers

from .models import Product



class ProductSerializer(serializers.ModelSerializer):

&nbsp;   class Meta:

&nbsp;       model = Product

&nbsp;       fields = "\_\_all\_\_"





➤ API View

💡 Example (views.py):



from rest\_framework.response import Response

from rest\_framework.decorators import api\_view

from .models import Product

from .serializers import ProductSerializer



@api\_view(\['GET'])

def product\_list(request):

&nbsp;   products = Product.objects.all()

&nbsp;   serializer = ProductSerializer(products, many=True)

&nbsp;   return Response(serializer.data)





➤ URL Setup

💡 Example (urls.py):



from django.urls import path

from .views import product\_list



urlpatterns = \[

&nbsp;   path('api/products/', product\_list),

]





➤ Run API



http://localhost:8000/api/products/





You will see JSON output ✅



➤ DRF Common Request Methods

| Method | Meaning          |

| ------ | ---------------- |

| GET    | Get data         |

| POST   | Create data      |

| PUT    | Update           |

| PATCH  | Partially update |

| DELETE | Delete           |



➤ DRF Permissions (Access Control)



Allow only authenticated users, admins, etc.



💡 Example: only logged-in users can access view



from rest\_framework.permissions import IsAuthenticated



Quick Summary



DRF helps build APIs



Uses serializers to convert DB ↔ JSON



Easy request methods (GET, POST, PUT, DELETE)



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 NEXT TOPIC: Django ModelViewSet – Beginner Notes



➤ What is a ModelViewSet?



A class in DRF that gives you full CRUD API automatically



Includes:



Create ✅



Read ✅



Update ✅



Delete ✅



So instead of writing many functions, you write one class 🎉



➤ Why use ModelViewSet?



Saves time ⏳



Cleaner code 🧼



Best for REST API development 🚀



➤ Example Setup



✅ views.py



from rest\_framework import viewsets

from .models import Product

from .serializers import ProductSerializer



class ProductViewSet(viewsets.ModelViewSet):

&nbsp;   queryset = Product.objects.all()

&nbsp;   serializer\_class = ProductSerializer





➤ Connect ViewSet to URLs



✅ urls.py



from rest\_framework.routers import DefaultRouter

from .views import ProductViewSet



router = DefaultRouter()

router.register('products', ProductViewSet)



urlpatterns = router.urls





Now this single code gives:

| Route               | Action         |

| ------------------- | -------------- |

| GET /products/      | List products  |

| POST /products/     | Create product |

| GET /products/1/    | Get one        |

| PUT /products/1/    | Update         |

| PATCH /products/1/  | Partial update |

| DELETE /products/1/ | Delete         |





🔥 No need to manually write each function!



➤ Important Notes



Must use a router to register



ModelViewSet + ModelSerializer = DRF POWER 💪



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Django Serializers (Beginner-Friendly Notes)



➤ What is a Serializer?



It converts Django model data 👉 JSON (data the API sends)



Also converts JSON 👉 Django model (data the API receives)



Think of it like a translator between Django \& API 😎



➤ Why do we need it?



APIs don't understand Python objects directly ❌



Serializers help exchange data in a format frontend/mobile can use ✅



➤ Types of Serializers



Serializer → manual fields



ModelSerializer → automatic fields (most used ✅)



➤ Example using ModelSerializer



✅ serializers.py



from rest\_framework import serializers

from .models import Product



class ProductSerializer(serializers.ModelSerializer):

&nbsp;   class Meta:

&nbsp;       model = Product

&nbsp;       fields = '\_\_all\_\_'





This will automatically include all fields in the Product model 🎯



➤ Custom fields example



✅ Add only specific fields



class ProductSerializer(serializers.ModelSerializer):

&nbsp;   class Meta:

&nbsp;       model = Product

&nbsp;       fields = \['id', 'name', 'price']





➤ Key Benefits



Less code 🧼



Handles validation 👍



Makes API development fast 🚀



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Django Request \& Response (Beginner-Friendly Notes)



➤ What is a Request?



A request is what the client (browser / app / frontend) sends to Django.



Example: When user clicks a button or visits a URL.



🧠 Think like this:

User → sends request → Django receives \& processes it ✅



➤ What is a Response?



A response is what Django sends back to the client.



Example: HTML page, JSON data, or error message.



🧠 Think like this:

Django → returns response → User sees result ✅



➤ Types of Requests



GET → fetch data (view page / get info)



POST → send data (submit form / login)



PUT → update data



DELETE → delete data



📌 Most common beginners use: GET \& POST



➤ Example in Django



✅ views.py



from django.http import HttpResponse



def hello(request):

&nbsp;   return HttpResponse("Hello, this is a response")





✅ Request: user visits /hello

✅ Response: Django returns "Hello, this is a response"



➤ JSON Response Example (For APIs)



from django.http import JsonResponse



def data(request):

&nbsp;   return JsonResponse({"name": "Menace", "course": "Django"})





➤ Important Notes



Request = input 📥



Response = output 📤



Django converts your code into web-friendly data ✅



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Django Models (Beginner-Friendly Notes)



➤ What are Models?



Models are Python classes that define your database structure.



They represent tables in the database.



Each attribute = a database column.



📌 Think of models as blueprints for storing data.



➤ Why Models Are Important



They let you work with a database using Python, not SQL.



Django automatically creates a database table from your model.



Makes data handling safe, easy \& fast ✅



➤ Common Model Fields



CharField → text



IntegerField → numbers



BooleanField → True/False



EmailField → emails



DateTimeField → date \& time



ForeignKey → relationship (link tables)



➤ Example (Simple Model) ✅



from django.db import models



class Student(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   age = models.IntegerField()

&nbsp;   email = models.EmailField()





🧠 Django will create a Student table with name, age, email columns.



➤ Creating the Table

After writing a model, run:



python manage.py makemigrations

python manage.py migrate





✅ Django now creates the table in the DB.



➤ Add Data Using Django Shell



python manage.py shell



from app.models import Student

Student.objects.create(name="John", age=20, email="john@gmail.com")





➤ Important Notes



Models = Database blueprint



Django ORM = query DB using Python



No need to write SQL manually 🎉



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 NEXT TOPIC: Django Admin (Beginner-Friendly Notes)



➤ What is Django Admin?



A built-in admin dashboard to manage your database.



Lets you add, edit, delete \& view data without writing code.



Works automatically once your models are created ✅



📌 Think of it as your project's control center.



➤ Why Use Django Admin?



Manage users \& data easily



No need to build your own dashboard



Great for testing \& development



➤ How to Activate Admin

Create a super-user:



python manage.py createsuperuser





Enter:



Username



Email (optional)



Password



Then run server:



python manage.py runserver





Open in browser:



http://127.0.0.1:8000/admin





Login with your superuser ✅



➤ Register Models in Admin Panel

To show your models in the admin dashboard:



➡️ In admin.py



from django.contrib import admin

from .models import Student



admin.site.register(Student)





Now Student model will appear in admin.



➤ Customizing Admin (Simple Example) ✅



class StudentAdmin(admin.ModelAdmin):

&nbsp;   list\_display = ('name', 'age', 'email')



admin.site.register(Student, StudentAdmin)





This shows name, age, email in list view.



➤ Important Notes



Admin = backend panel 🖥️



Use super-user to login 🔐



Must register models to see them



Very useful for testing data 🧪



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Understanding Django \_\_str\_\_() Method



➤ What is \_\_str\_\_() in Django?



A special method used inside models



Controls how your object is displayed when printed or shown in admin panel



📌 Without it, objects look like this in admin:



Student object (1)





With \_\_str\_\_() — looks clean \& readable ✅



➤ Why is \_\_str\_\_() Important?



Makes admin panel easy to understand



Helps identify objects quickly



Improves debugging clarity



➤ Simple Example



✅ models.py



class Student(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   age = models.IntegerField()



&nbsp;   def \_\_str\_\_(self):

&nbsp;       return self.name





Now admin will show:



John

Mary

David





Instead of Student Object (1) 🎉



➤ Another Example: Multiple Fields



def \_\_str\_\_(self):

&nbsp;   return f"{self.name} ({self.age})"





Output:



John (21)





➤ Remember



\_\_str\_\_() runs automatically when object displays



Always use it for readable output



Return string only (not numbers)



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 NEXT TOPIC: Django Model Relationships (Beginner-Friendly Notes)



➤ What are Model Relationships?

They allow database tables to connect to each other — like linking users to posts, customers to orders, etc.



Django provides 3 main relationship types 👇



➤ 1️⃣ One-to-One Relationship



One record ↔ One record



Example: Each user has one profile



✅ Example



class Profile(models.Model):

&nbsp;   user = models.OneToOneField(User, on\_delete=models.CASCADE)

&nbsp;   bio = models.TextField()





➤ 2️⃣ One-to-Many (Foreign Key)



One record ↔ Many records



Example: One author can have many blog posts



✅ Example



class Post(models.Model):

&nbsp;   author = models.ForeignKey(User, on\_delete=models.CASCADE)

&nbsp;   title = models.CharField(max\_length=100)





➤ 3️⃣ Many-to-Many



Many records ↔ Many records



Example: A student can enroll in many courses, and a course can have many students



✅ Example



class Course(models.Model):

&nbsp;   students = models.ManyToManyField(User)





➤ Why Relationships Matter



Structure your data properly



Avoid data duplication



Efficient database queries



Enable real-world app logic



➤ Remember

| Relationship | Meaning           | Example            |

| ------------ | ----------------- | ------------------ |

| One-to-One   | One item per item | User ↔ Profile     |

| One-to-Many  | One owns many     | User → Posts       |

| Many-to-Many | Many share many   | Students ↔ Courses |



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 NEXT TOPIC: Django Migration System (Beginner-Friendly Notes)



➤ What Are Migrations?

Migrations are Django’s way of saving changes you make to your models (database tables).

They update your database when you add, edit, or delete fields/models.



Think of migrations as database version control ✅



➤ Why Migrations Are Important



Create tables in DB



Update DB when models change



Keep DB structure correct



Work as teamwork-friendly record of model changes



➤ Common Migration Commands



Action	Command

Detect new model changes	python manage.py makemigrations

Apply changes to DB	python manage.py migrate

Show migration history	python manage.py showmigrations



➤ Typical Workflow



\# After editing models.py

python manage.py makemigrations  

python manage.py migrate





➤ Example



class Product(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   price = models.IntegerField()





After writing this model 👆

You run:



python manage.py makemigrations

python manage.py migrate





This creates a Product table in your database ✅



➤ Key Notes



You must run migrations after changing models



Django automatically tracks and applies changes



Without migrate → models won't exist in the database



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Django Superuser (Beginner-Friendly Notes)



➤ What is a Superuser?

A superuser in Django is the highest-level admin account.

It has full access to the Django Admin panel — can manage users, data, permissions, and everything.



Like the “owner” role in a system ✅



➤ Why You Need It



Access /admin



Manage all database models



Create/modify/delete users



Full website control



➤ How to Create a Superuser



Run this command 👇



python manage.py createsuperuser





Then enter:



Username



Email



Password (you won't see characters while typing — normal!)



➤ Login to Admin Panel

Start your server



python manage.py runserver





Then go to:



http://127.0.0.1:8000/admin





Login using your superuser credentials ✅



➤ Important Note

Superuser has all permissions — be careful when sharing login details 🔐



This is the account you use to manage the whole site.



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 NEXT TOPIC: Django Static Files (Beginner-Friendly Notes)



➤ What are Static Files?

Static files are files that don’t change when your app runs.

They are used to make your website look good and work nicely ✅



Examples:



CSS (styling) 🎨



JavaScript (client scripts) ⚙️



Images / Icons 🖼️



Fonts 🔤



➤ Why Static Files Are Important

They help you add:



Colors \& layout



Animations



Logos \& pictures



Buttons \& menus



Django needs a proper setup to access them in the browser.



➤ Where to Store Static Files

Inside your app, create a folder named static/ 👇



Example folder structure:



myapp/

&nbsp;└── static/

&nbsp;     └── myapp/

&nbsp;          └── styles.css





➤ How to Load Static Files in Django Template



✅ Step 1: Load static tag at the top of your HTML



{% load static %}





✅ Step 2: Link CSS file



<link rel="stylesheet" href="{% static 'myapp/styles.css' %}">





✅ Step 3: Display an image



<img src="{% static 'myapp/logo.png' %}" alt="Logo">





➤ Settings Needed in settings.py

Make sure this is present 👇



STATIC\_URL = '/static/'





For production you will later use:



STATICFILES\_DIRS = \[ BASE\_DIR / 'static' ]

STATIC\_ROOT = BASE\_DIR / 'staticfiles'





(Don’t worry — you’ll learn that later 🙂)



✅ Example in real Django project



{% load static %}

<link rel="stylesheet" href="{% static 'css/main.css' %}">

<img src="{% static 'images/banner.jpg' %}">





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Django Admin – register() Explanation (Beginner Friendly)



📌 What is admin.site.register()?



admin.site.register() is the function Django uses to tell the admin panel about your model, so it shows up in the admin dashboard.



Without registering your model, Django doesn't know it should appear in the admin.



⚙️ How it Works



Imagine Django Admin is like a shop manager.

Your models (Product, Order, UserProfile) are new items.



To display these items in the shop manager dashboard, you must register them 👇



🧠 Example

✅ Registering a Model (Basic)

\# admin.py

from django.contrib import admin

from .models import Product



admin.site.register(Product)





Meaning:

Hey Django, please show the Product model in the admin panel.



✅ Registering a Model with Admin Customization

\# admin.py

from django.contrib import admin

from .models import Product



class ProductAdmin(admin.ModelAdmin):

&nbsp;   list\_display = ('name', 'price', 'stock')

&nbsp;   search\_fields = ('name',)



admin.site.register(Product, ProductAdmin)





Meaning:

We are not just showing Product in admin…

We are giving it admin settings like:



✅ Show name, price \& stock in list table



✅ Allow admin search by product name



🤓 Beginner Memory Trick



| Term                                       | Meaning                          |

| ------------------------------------------ | -------------------------------- |

| 📦 Model                                   | Your database table              |

| 🛠 admin.py                                | Where you connect model to admin |

| ✅ `admin.site.register(Model)`             | Show model in admin              |

| ✨ `admin.site.register(Model, ModelAdmin)` | Show model + admin features      |



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Django Templates (Beginner-Friendly Notes)



Django Templates are the frontend files in Django — where you write HTML mixed with Django template language.



They help you display data from your backend to users.



📌 What is a Template in Django?



A template is an HTML file that Django uses to show pages in the browser.



Templates can:



Show text and images ✅



Display dynamic content from database ✅



Use loops \& conditions ✅



📌 Setting Up Templates Folder



Inside your project, create:



project\_folder/

&nbsp;└── templates/

&nbsp;      └── home.html





Then tell Django where templates are located — open settings.py:



TEMPLATES = \[

&nbsp;   {

&nbsp;       'DIRS': \[BASE\_DIR / 'templates'],

&nbsp;   }

]





Now Django knows where your HTML files live. ✅



📌 Sending a Template From Views



views.py example:



from django.shortcuts import render



def home(request):

&nbsp;   return render(request, 'home.html')





📌 render() connects view + template



🧾 Template Example (home.html)

<!DOCTYPE html>

<html>

<head>

&nbsp;   <title>Welcome</title>

</head>

<body>

&nbsp;   <h1>Hello Django Beginner 👋</h1>

</body>

</html>





Open in browser and you'll see the page!



📌 Dynamic Content Example (Passing Data to Template)

views.py

def home(request):

&nbsp;   context = {"name": "MenACE"}

&nbsp;   return render(request, 'home.html', context)



home.html

<h1>Hello {{ name }}</h1>





🧠 {{ name }} prints value passed from view



🤓 Memory Trick



| Symbol     | Meaning                             |

| ---------- | ----------------------------------- |

| `{{ }}`    | Display data                        |

| `{% %}`    | Logic (loops, if, extends, include) |

| `render()` | Connects view → template            |





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 NEXT TOPIC: Django Template Tags ({{ }} \& {% %})



Template tags allow you to write Python-like logic inside HTML.



📌 Types of Template Tags

Tag	Meaning

{{ }}	Display variables / data

{% %}	Logic (if, for loop, include, extends, csrf\_token, etc.)

📌 Displaying Data ({{ }})



Used to show a value from views:



views.py

def dashboard(request):

&nbsp;   return render(request, 'dashboard.html', {"username": "MenACE"})



dashboard.html

<h2>Hello {{ username }} 👋</h2>



📌 Logic Example ({% %})

Loop

{% for item in products %}

&nbsp; <p>{{ item }}</p>

{% endfor %}



If condition

{% if user.is\_authenticated %}

&nbsp; <p>Welcome back!</p>

{% else %}

&nbsp; <p>Please log in</p>

{% endif %}





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 NEXT TOPIC: Template Inheritance (extends base.html)



Template inheritance lets you create one master layout (header, navbar, footer) and reuse it.



📌 Why Use It?



✅ Avoid repeating HTML

✅ Keep navbar/footer in one place

✅ Cleaner code



📌 Base Template Example (base.html)

<!DOCTYPE html>

<html>

<head>

&nbsp; <title>Django App</title>

</head>

<body>



{% include 'navbar.html' %}



<div>

&nbsp; {% block content %}

&nbsp; {% endblock %}

</div>



</body>

</html>



📌 Child Template Example (home.html)

{% extends 'base.html' %}



{% block content %}

<h1>Welcome Home 🏠</h1>

<p>This is the home page.</p>

{% endblock %}





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 NEXT TOPIC: Including Templates (include)



Include lets you reuse small parts like:



✅ Navbar



✅ Footer



✅ Sidebar



✅ Alerts/messages



📌 Example: Include Navbar

navbar.html

<nav>

&nbsp; <a href="/">Home</a> |

&nbsp; <a href="/about">About</a>

</nav>



base.html

{% include 'navbar.html' %}



📌 You Can Reuse Components Anywhere

{% include 'footer.html' %}





No copy-paste ✅ Reusable ✅ Clean project ✅



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Django Forms



📌 What are Django Forms?

Django Forms help collect and validate input from users (like login form, register form, contact form).



📌 Why use Django Forms?



Handle user input safely



Validate fields (email, required fields, etc.)



Save data to database easily



📌 Two types of forms



Forms → Regular forms (not tied to models)



ModelForms → Forms directly linked to database models ✅ (most common)



📌 Regular Django Form



🧾 Example



from django import forms



class ContactForm(forms.Form):

&nbsp;   name = forms.CharField(max\_length=100)

&nbsp;   email = forms.EmailField()

&nbsp;   message = forms.CharField(widget=forms.Textarea)



📌 Model Form



🧾 Example



from django import forms

from .models import Seller



class SellerForm(forms.ModelForm):

&nbsp;   class Meta:

&nbsp;       model = Seller

&nbsp;       fields = \['full\_name', 'store\_name', 'phone']



📌 Display Form in View



🧾 Example



from django.shortcuts import render

from .forms import ContactForm



def contact\_view(request):

&nbsp;   form = ContactForm()

&nbsp;   return render(request, 'contact.html', {'form': form})



📌 Template Display Form



🧾 Example



<form method="POST">

&nbsp; {% csrf\_token %}

&nbsp; {{ form.as\_p }}

&nbsp; <button type="submit">Submit</button>

</form>





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Django Models Deep Dive



📌 What are Models?

Models are Python classes that represent database tables in Django.



📌 Purpose of Models



Store data in database



Define fields (name, email, price, etc.)



Interact with database easily (no SQL needed)



📌 Model Basic Structure



🧾 Example



from django.db import models



class Product(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   price = models.DecimalField(max\_digits=10, decimal\_places=2)

&nbsp;   in\_stock = models.BooleanField(default=True)



&nbsp;   def \_\_str\_\_(self):

&nbsp;       return self.name





✅ This creates a Product table with name, price, stock status.



📌 Common Field Types



| Field                     | Meaning                    |

| ------------------------- | -------------------------- |

| CharField                 | Text (short)               |

| TextField                 | Long text (description)    |

| IntegerField              | Whole number               |

| FloatField / DecimalField | Numbers with decimals      |

| BooleanField              | True/False                 |

| DateTimeField             | Date + Time                |

| EmailField                | Email validation           |

| ForeignKey                | Relationship (Many-to-One) |

| OneToOneField             | Unique relationship        |

| ManyToManyField           | Many to many               |





📌 One-to-One Relationship



🧾 Example



class UserProfile(models.Model):

&nbsp;   user = models.OneToOneField(User, on\_delete=models.CASCADE)

&nbsp;   bio = models.TextField()





👆 One user has one profile.



📌 Foreign Key (Many-to-One)



🧾 Example



class Order(models.Model):

&nbsp;   user = models.ForeignKey(User, on\_delete=models.CASCADE)

&nbsp;   product = models.CharField(max\_length=100)





👆 Many orders can belong to 1 user.



📌 Many-to-Many



🧾 Example



class Student(models.Model):

&nbsp;   name = models.CharField(max\_length=100)



class Course(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   students = models.ManyToManyField(Student)





👆 Students can join many courses \& vice-versa



📌 Save data to DB



🧾 Example



product = Product(name="Shoes", price=50)

product.save()



📌 Django ORM Queries



🧾 Example



Product.objects.all()           # Get all

Product.objects.filter(price=50)

Product.objects.get(id=1)

Product.objects.create(name="Bag", price=80)





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 Static Files in Django



📌 What are Static Files?

Static files are files used in your website that do not change with user input.



Examples:



CSS



JavaScript



Images



Logos / Icons



📌 Why do we use Static Files?

To style pages, add scripts, and show images in Django templates.



📌 Static Folder Setup



🧾 Example — settings.py



STATIC\_URL = '/static/'

STATICFILES\_DIRS = \[

&nbsp;   BASE\_DIR / "static"

]





📂 Folder structure



project/

&nbsp;└── static/

&nbsp;     ├── css/

&nbsp;     ├── js/

&nbsp;     └── images/



📌 Using static files in template



🧾 Example — Template



{% load static %}



<link rel="stylesheet" href="{% static 'css/style.css' %}">

<img src="{% static 'images/logo.png' %}" alt="logo">

<script src="{% static 'js/app.js' %}"></script>



📌 CSS Example



🧾 Example — static/css/style.css



body {

&nbsp; background: lightgray;

}



📌 Static in Production



When deploying (like on Render, Vercel, or DigitalOcean), use:



python manage.py collectstatic





This gathers all static files into one folder for production.



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Django Authentication (Login / Register)



📌 What is Authentication?

Authentication means verifying who the user is

(Example: Login with username + password)



📌 Why do we need it?



Secure your website



Allow user accounts



Restrict access to certain pages



📌 Built-in Django Auth System



Django already provides:



✅ Login

✅ Logout

✅ Register (User creation)

✅ Password hashing

✅ User model

✅ Permissions (staff, admin, etc.)



📌 Register User (Signup)



🧾 Example — views.py



from django.contrib.auth.models import User

from django.contrib.auth import login

from django.shortcuts import render, redirect



def register\_user(request):

&nbsp;   if request.method == "POST":

&nbsp;       username = request.POST\["username"]

&nbsp;       password = request.POST\["password"]

&nbsp;       

&nbsp;       user = User.objects.create\_user(username=username, password=password)

&nbsp;       user.save()

&nbsp;       login(request, user)

&nbsp;       return redirect('home')



&nbsp;   return render(request, "register.html")





🧾 Example — register.html



<form method="POST">

&nbsp; {% csrf\_token %}

&nbsp; <input type="text" name="username" placeholder="Username">

&nbsp; <input type="password" name="password" placeholder="Password">

&nbsp; <button type="submit">Register</button>

</form>



📌 Login User



🧾 Example — views.py



from django.contrib.auth import authenticate, login



def login\_user(request):

&nbsp;   if request.method == "POST":

&nbsp;       username = request.POST\["username"]

&nbsp;       password = request.POST\["password"]



&nbsp;       user = authenticate(request, username=username, password=password)



&nbsp;       if user:

&nbsp;           login(request, user)

&nbsp;           return redirect('home')

&nbsp;       else:

&nbsp;           return render(request, "login.html", {"error": "Invalid credentials"})



&nbsp;   return render(request, "login.html")





🧾 Example — login.html



<form method="POST">

&nbsp; {% csrf\_token %}

&nbsp; <input type="text" name="username" placeholder="Username">

&nbsp; <input type="password" name="password" placeholder="Password">

&nbsp; <button type="submit">Login</button>

</form>



📌 Logout User



🧾 Example — views.py



from django.contrib.auth import logout

from django.shortcuts import redirect



def logout\_user(request):

&nbsp;   logout(request)

&nbsp;   return redirect('login')



📌 Restrict page to logged-in users



🧾 Example



from django.contrib.auth.decorators import login\_required



@login\_required

def dashboard(request):

&nbsp;   return render(request, "dashboard.html")





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 CRUD Operations in Django



CRUD = basic database actions:



Action	Meaning	Django Method

C	Create	create() / save()

R	Read	get() / filter() / all()

U	Update	Change then save()

D	Delete	delete()



Used to manage data (users, products, posts, etc.)



📌 Model Example to Use for CRUD

from django.db import models



class Task(models.Model):

&nbsp;   title = models.CharField(max\_length=200)

&nbsp;   completed = models.BooleanField(default=False)



&nbsp;   def \_\_str\_\_(self):

&nbsp;       return self.title



✅ CREATE (Add new item)



🧾 View



def create\_task(request):

&nbsp;   if request.method == "POST":

&nbsp;       title = request.POST\["title"]

&nbsp;       Task.objects.create(title=title)

&nbsp;       return redirect('task\_list')



&nbsp;   return render(request, "create\_task.html")





🧾 Template



<form method="POST">

&nbsp; {% csrf\_token %}

&nbsp; <input type="text" name="title" placeholder="Task title">

&nbsp; <button type="submit">Add Task</button>

</form>



✅ READ (Show items)



🧾 View



def task\_list(request):

&nbsp;   tasks = Task.objects.all()

&nbsp;   return render(request, "task\_list.html", {"tasks": tasks})





🧾 Template



<ul>

&nbsp; {% for task in tasks %}

&nbsp;   <li>{{ task.title }}</li>

&nbsp; {% endfor %}

</ul>



✅ UPDATE (Edit item)



🧾 View



def update\_task(request, id):

&nbsp;   task = Task.objects.get(id=id)



&nbsp;   if request.method == "POST":

&nbsp;       task.title = request.POST\["title"]

&nbsp;       task.save()

&nbsp;       return redirect('task\_list')



&nbsp;   return render(request, "update\_task.html", {"task": task})





🧾 Template



<form method="POST">

&nbsp; {% csrf\_token %}

&nbsp; <input type="text" name="title" value="{{ task.title }}">

&nbsp; <button type="submit">Update</button>

</form>



✅ DELETE (Remove item)



🧾 View



def delete\_task(request, id):

&nbsp;   task = Task.objects.get(id=id)

&nbsp;   task.delete()

&nbsp;   return redirect('task\_list')





🧾 Template



<a href="{% url 'delete\_task' task.id %}">Delete</a>





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 What is REST?



📌 Meaning

REST = Representational State Transfer



📌 Simple Explanation

REST is a way for computers/systems to communicate over the internet using standard rules.



📌 Why use REST?



Allows backend to talk to frontend (React, mobile app, etc.)



Sends data, not HTML



Very fast \& lightweight



📌 Format

REST APIs send data mostly in JSON



🧾 Example (Normal Website vs REST API)



| Normal Django      | REST API                             |

| ------------------ | ------------------------------------ |

| Returns HTML pages | Returns JSON data                    |

| For web browsers   | For apps, websites, backend services |

| Uses templates     | Uses serializers \& views             |



🧾 REST API JSON Example



User requests data from /api/products/



API responds with:



\[

&nbsp; {

&nbsp;   "id": 1,

&nbsp;   "name": "Laptop",

&nbsp;   "price": 1500

&nbsp; },

&nbsp; {

&nbsp;   "id": 2,

&nbsp;   "name": "Phone",

&nbsp;   "price": 900

&nbsp; }

]





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 REST vs RESTful



📌 REST

REST is the architecture style or rules for building APIs.



📌 RESTful

RESTful is an API that follows those REST rules correctly.



Think of it like:



| Term    | Meaning                       |

| ------- | ----------------------------- |

| REST    | The rules/book                |

| RESTful | A system that obeys the rules |



📌 Rules of a RESTful API



✅ Uses HTTP methods (GET, POST, PUT, DELETE)

✅ Uses URLs as resources (not actions)

✅ Returns JSON data

✅ Stateless → server does not remember previous requests

✅ Client \& server separate (frontend \& backend independent)



🧾 Example



❌ Not RESTful



/getProducts

/addProduct

/updateProduct





✅ RESTful



GET    /products

POST   /products

PUT    /products/1

DELETE /products/1





🎯 Same endpoint, different method = different action



Simple Analogy



REST = School Rules

RESTful = Student following school rules ✅



If an API follows REST rules → It is RESTful.



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 HTTP Methods (GET, POST, PUT, DELETE)



📌 What are HTTP Methods?

HTTP methods tell the server what action you want to do.



These are the 4 most important in REST APIs:



| Method | Meaning     | Use                     |

| ------ | ----------- | ----------------------- |

| GET    | Fetch data  | Read data               |

| POST   | Create data | Add new record          |

| PUT    | Update data | Edit an existing record |

| DELETE | Remove data | Delete a record         |



🧾 Example API URL



| Method | URL                | Action                   |

| ------ | ------------------ | ------------------------ |

| GET    | `/api/products/`   | Get all products         |

| POST   | `/api/products/`   | Add product              |

| PUT    | `/api/products/1/` | Update product with ID 1 |

| DELETE | `/api/products/1/` | Delete product with ID 1 |



📌 Real JSON responses



🧾 GET Response



{

&nbsp; "id": 1,

&nbsp; "name": "iPhone",

&nbsp; "price": 1200

}





🧾 POST Body (Sending data)



{

&nbsp; "name": "Laptop",

&nbsp; "price": 2500

}





🧾 PUT Body (Updating item)



{

&nbsp; "price": 2000

}





🧾 DELETE

No body — just delete the record.





📌 Beginner Memory Trick



| Action | Think like                   |

| ------ | ---------------------------- |

| GET    | “Show me things”             |

| POST   | “I want to add something”    |

| PUT    | “I want to modify something” |

| DELETE | “Remove it”                  |



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 API Endpoints



📌 What is an API Endpoint?

An endpoint is a URL where your API can be accessed.



It tells the system which resource you want.



Example resource: products, users, orders, blogs, etc.



📌 Simple Explanation

Endpoint = Address where data lives.



🧾 Examples of Endpoints



| Endpoint         | Meaning            |

| ---------------- | ------------------ |

| `/api/products/` | Work with products |

| `/api/users/`    | Work with users    |

| `/api/orders/`   | Work with orders   |





📌 Endpoint + HTTP Method = Action



| Method | Endpoint           | Action                |

| ------ | ------------------ | --------------------- |

| GET    | `/api/products/`   | Get all products      |

| POST   | `/api/products/`   | Create product        |

| GET    | `/api/products/1/` | Get product with ID 1 |

| PUT    | `/api/products/1/` | Update product 1      |

| DELETE | `/api/products/1/` | Delete product 1      |





📌 Real Example (Browser / Postman)



Request:



GET /api/products/





Response:



\[

&nbsp; {"id": 1, "name": "Phone"},

&nbsp; {"id": 2, "name": "Tablet"}

]



✅ Naming Best Practice



Use plural names for resources:



❌ /product

✅ /products



🎯 Summary



Endpoints = location of your data.

Methods tell what action to take on that location.



Like:

📍Store address (Endpoint)

🛒 Buy, return, check price (HTTP methods)



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 JSON Response



📌 What is JSON?

JSON = JavaScript Object Notation

It is the format REST APIs use to send data.



📌 Why JSON?



Easy to read 📖



Lightweight ⚡



Works with frontend (React, Mobile apps, Vue, etc.)



📌 What does JSON look like?

It’s basically Python dictionary style but used on the web.



🧾 JSON Example (Single Object)

{

&nbsp; "id": 1,

&nbsp; "name": "Laptop",

&nbsp; "price": 1500,

&nbsp; "in\_stock": true

}



🧾 JSON Example (List of Objects)

\[

&nbsp; {

&nbsp;   "id": 1,

&nbsp;   "name": "Laptop",

&nbsp;   "price": 1500

&nbsp; },

&nbsp; {

&nbsp;   "id": 2,

&nbsp;   "name": "Phone",

&nbsp;   "price": 900

&nbsp; }

]



📌 JSON vs Python Dictionary





| JSON              | Python                     |

| ----------------- | -------------------------- |

| `true`            | `True`                     |

| `false`           | `False`                    |

| `null`            | `None`                     |

| Strings use `" "` | Strings use `' '` or `" "` |





📌 JSON in Django (basic example)



🧾 Returning JSON without DRF:



from django.http import JsonResponse



def example(request):

&nbsp;   data = {"name": "John", "age": 25}

&nbsp;   return JsonResponse(data)





✅ DRF will make this even easier soon.



📌 Where you'll see JSON



| Tool          | Purpose                       |

| ------------- | ----------------------------- |

| Browser       | View simple GET API responses |

| Postman       | Test APIs                     |

| Frontend Apps | Receive API data              |



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 DRF Serializers



📌 What is a Serializer?

A serializer converts Django models (Python objects) into JSON so APIs can send data to frontend.



📌 Why do we need Serializers?



Convert Python/Django data → JSON ✅



Validate incoming data (like forms) ✅



Save data to the database ✅



Think of a serializer as a bridge between database and API response.



📌 Types of Serializers in DRF





| Type                | Usage                                              |

| ------------------- | -------------------------------------------------- |

| `Serializer`        | Manual fields (custom control)                     |

| `ModelSerializer` ✅ | Auto create fields from model (recommended \& easy) |







🧾 Step-by-Step Example

1️⃣ Create a Model

\# models.py

from django.db import models



class Product(models.Model):

&nbsp;   name = models.CharField(max\_length=100)

&nbsp;   price = models.DecimalField(max\_digits=6, decimal\_places=2)



2️⃣ Create Serializer

\# serializers.py

from rest\_framework import serializers

from .models import Product



class ProductSerializer(serializers.ModelSerializer):

&nbsp;   class Meta:

&nbsp;       model = Product

&nbsp;       fields = \['id', 'name', 'price']





✅ Now DRF can convert our Product model to JSON.



3️⃣ Use Serializer in View



We'll learn API views later, but here’s a preview:



\# views.py

from rest\_framework.response import Response

from .models import Product

from .serializers import ProductSerializer



def get\_products(request):

&nbsp;   products = Product.objects.all()

&nbsp;   serializer = ProductSerializer(products, many=True)

&nbsp;   return Response(serializer.data)



📌 What serializer.data gives

\[

&nbsp; {"id": 1, "name": "Laptop", "price": "1500.00"},

&nbsp; {"id": 2, "name": "Phone", "price": "900.00"}

]



✅ Key Points to Remember



| Concept           | Meaning                  |

| ----------------- | ------------------------ |

| Model             | Structure of data in DB  |

| Serializer        | Converts DB data ↔ JSON  |

| `many=True`       | Serializing many records |

| `serializer.data` | Output JSON data         |





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End





🎯 DRF Views (APIView \& ViewSet)



📌 What are Views in DRF?

Views are functions/classes that handle API requests and return JSON responses.



They control how the API behaves.



📌 Types of DRF Views



| View Type   | Description                                |

| ----------- | ------------------------------------------ |

| `APIView`   | Manual control — we define GET, POST, etc. |

| `ViewSet` ✅ | DRF handles CRUD automatically (easier)    |





We will learn both, because real developers use ViewSets a lot.



✅ APIView (Manual Control)



📌 Best when you want full custom logic.



🧾 Example — APIView

views.py

from rest\_framework.views import APIView

from rest\_framework.response import Response

from .models import Product

from .serializers import ProductSerializer



class ProductAPI(APIView):

&nbsp;   def get(self, request):

&nbsp;       products = Product.objects.all()

&nbsp;       serializer = ProductSerializer(products, many=True)

&nbsp;       return Response(serializer.data)



&nbsp;   def post(self, request):

&nbsp;       serializer = ProductSerializer(data=request.data)

&nbsp;       if serializer.is\_valid():

&nbsp;           serializer.save()

&nbsp;           return Response(serializer.data)

&nbsp;       return Response(serializer.errors)



🧾 URL

from django.urls import path

from .views import ProductAPI



urlpatterns = \[

&nbsp;   path('products/', ProductAPI.as\_view()),

]





✅ Handles GET + POST manually



✅ ViewSet (Faster \& Cleaner)



📌 Best for CRUD APIs quickly



🧾 Example — ViewSet

views.py

from rest\_framework.viewsets import ModelViewSet

from .models import Product

from .serializers import ProductSerializer



class ProductViewSet(ModelViewSet):

&nbsp;   queryset = Product.objects.all()

&nbsp;   serializer\_class = ProductSerializer





⬆ No GET, POST, PUT, DELETE method needed — DRF does it automatically!



📌 Add Router for ViewSet

urls.py

from rest\_framework.routers import DefaultRouter

from .views import ProductViewSet



router = DefaultRouter()

router.register('products', ProductViewSet)



urlpatterns = router.urls





✅ Instantly gives:



| Method | Endpoint       |

| ------ | -------------- |

| GET    | `/products/`   |

| POST   | `/products/`   |

| GET    | `/products/1/` |

| PUT    | `/products/1/` |

| DELETE | `/products/1/` |





🎯 Summary



| Feature     | APIView             | ViewSet          |

| ----------- | ------------------- | ---------------- |

| Control     | Full manual control | Auto CRUD        |

| Code length | More                | Less ✅           |

| Use case    | Custom logic        | Fast CRUD APIs ✅ |





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Routers in Django REST Framework



📌 What is a Router?

A Router automatically creates URL routes for your ViewSets.



📌 Why use Routers?



No need to manually write URLs for CRUD



Cleaner code



Less mistakes



Saves time 🚀



✅ Without Router (Manual URLs)

path('products/', ProductViewSet.as\_view({'get':'list', 'post':'create'})),

path('products/<int:pk>/', ProductViewSet.as\_view({'get':'retrieve','put':'update','delete':'destroy'})),





❌ Lots of code

❌ Hard to maintain



✅ With Router (Recommended)

views.py

from rest\_framework.viewsets import ModelViewSet

from .models import Product

from .serializers import ProductSerializer



class ProductViewSet(ModelViewSet):

&nbsp;   queryset = Product.objects.all()

&nbsp;   serializer\_class = ProductSerializer



urls.py

from rest\_framework.routers import DefaultRouter

from .views import ProductViewSet



router = DefaultRouter()

router.register("products", ProductViewSet)



urlpatterns = router.urls





✅ Auto-generates all API routes:



| Method | Endpoint       | Action       |

| ------ | -------------- | ------------ |

| GET    | `/products/`   | List all     |

| POST   | `/products/`   | Create       |

| GET    | `/products/1/` | Retrieve one |

| PUT    | `/products/1/` | Update       |

| DELETE | `/products/1/` | Delete       |





📌 Router Types



| Router            | Use                               |

| ----------------- | --------------------------------- |

| `DefaultRouter` ✅ | Adds `/products/` + browsable API |

| `SimpleRouter`    | Same but no default API root page |



🎯 Memory Trick



Router = Auto URL generator for ViewSets



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Middleware (Short Note)



📌 Definition

Middleware is a layer between request and response in Django.

It can process requests before views run and modify responses before sending them back.



📌 Purpose / Use Cases



Handle authentication \& permissions



Log requests or responses



Modify request or response data



Block certain users or IPs



Global error handling (404, 500)



📌 Example in settings.py



MIDDLEWARE = \[

&nbsp;   'django.middleware.security.SecurityMiddleware',

&nbsp;   'django.contrib.sessions.middleware.SessionMiddleware',

&nbsp;   'django.middleware.common.CommonMiddleware',

]





📌 Simple Analogy

Middleware = gatekeeper or checkpoint

Requests → Gatekeeper → Views → Gatekeeper → Response



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 JWT Authentication (JSON Web Token)



JWT is a token-based authentication system for APIs.



Instead of Django sessions, the server issues a token after login.

The client sends this token on every request to prove identity.



🔑 Key Parts of JWT



| Part      | Purpose                                    |

| --------- | ------------------------------------------ |

| Header    | Information about algorithm and token type |

| Payload   | Contains user info / claims                |

| Signature | Ensures token is not tampered              |





Example token:



eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoxfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV\_adQssw5c



⚡ Setup JWT in Django



1️⃣ Install package:



pip install djangorestframework-simplejwt





2️⃣ Add in settings.py:



REST\_FRAMEWORK = {

&nbsp;   'DEFAULT\_AUTHENTICATION\_CLASSES': (

&nbsp;       'rest\_framework\_simplejwt.authentication.JWTAuthentication',

&nbsp;   )

}



🔑 Token Views



Add in urls.py:



from rest\_framework\_simplejwt.views import (

&nbsp;   TokenObtainPairView,

&nbsp;   TokenRefreshView,

)



urlpatterns = \[

&nbsp;   path('api/token/', TokenObtainPairView.as\_view(), name='token\_obtain\_pair'),

&nbsp;   path('api/token/refresh/', TokenRefreshView.as\_view(), name='token\_refresh'),

]





/api/token/ → Get access + refresh token



/api/token/refresh/ → Get new access token using refresh token



🧾 Example: Get Token



POST /api/token/ with:



{

&nbsp; "username": "testuser",

&nbsp; "password": "123456"

}





Response:



{

&nbsp; "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...",

&nbsp; "refresh": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9..."

}





✅ Access = short-lived token (minutes)

🔁 Refresh = long-lived token (used to get new access)



🔑 Using JWT in API Requests



Add header:



Authorization: Bearer <access\_token>





Example with Postman / frontend:



GET /api/products/

Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...



🔒 Protecting Views with JWT

from rest\_framework.permissions import IsAuthenticated

from rest\_framework.views import APIView

from rest\_framework.response import Response



class DashboardView(APIView):

&nbsp;   permission\_classes = \[IsAuthenticated]



&nbsp;   def get(self, request):

&nbsp;       return Response({"message": f"Hello {request.user.username}"})





✅ Only requests with valid JWT can access this view.



🔄 Refresh Token Example



POST /api/token/refresh/ with:



{

&nbsp; "refresh": "<refresh\_token\_here>"

}





Response:



{

&nbsp; "access": "<new\_access\_token\_here>"

}



🎯 Summary



| Term          | Meaning                          |

| ------------- | -------------------------------- |

| JWT           | Token that proves user identity  |

| Access Token  | Short-lived token for requests   |

| Refresh Token | Long-lived token to renew access |

| Bearer Token  | Sent in request headers          |





🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 JWT Authentication (DRF)



📌 What it is:

JWT Authentication is the mechanism by which DRF checks incoming API requests for a valid JWT token and identifies the user.



It replaces session-based authentication for APIs.



🔑 How it Works (Step-by-Step)



1️⃣ User logs in → API issues access + refresh token

2️⃣ User sends access token in Authorization: Bearer <token> header for every request

3️⃣ DRF’s JWTAuthentication class intercepts request

4️⃣ Token is decoded → verify signature + expiration

5️⃣ DRF sets request.user and request.auth if token is valid

6️⃣ If invalid/expired → DRF returns 401 Unauthorized



⚙️ DRF Settings for JWT



In settings.py:



REST\_FRAMEWORK = {

&nbsp;   'DEFAULT\_AUTHENTICATION\_CLASSES': (

&nbsp;       'rest\_framework\_simplejwt.authentication.JWTAuthentication',

&nbsp;   )

}





This tells DRF to look for JWT tokens in the Authorization header



Handles token decoding automatically ✅



📌 Example: Protecting a View

from rest\_framework.views import APIView

from rest\_framework.response import Response

from rest\_framework.permissions import IsAuthenticated



class DashboardView(APIView):

&nbsp;   permission\_classes = \[IsAuthenticated]



&nbsp;   def get(self, request):

&nbsp;       return Response({

&nbsp;           "message": f"Hello {request.user.username}, welcome to your dashboard!"

&nbsp;       })





Only requests with valid JWT tokens can access



request.user is automatically populated



🔄 Refreshing Access Token



1️⃣ Access token expires (e.g., 5 min)

2️⃣ Client sends refresh token to /token/refresh/

3️⃣ DRF returns a new access token

4️⃣ User stays logged in without re-entering credentials



🛡️ Optional: Blacklist / Logout



Install blacklist support:



pip install djangorestframework-simplejwt\[blacklist]





Add to settings.py:



SIMPLE\_JWT = {

&nbsp;   'BLACKLIST\_AFTER\_ROTATION': True,

}





Blacklist allows logging out users by invalidating refresh tokens.



📌 Example Request Flow (JWT Authentication)



| Step | Endpoint          | Action                                   |

| ---- | ----------------- | ---------------------------------------- |

| POST | `/login/`         | Get access + refresh token               |

| GET  | `/me/`            | Access protected route with access token |

| POST | `/token/refresh/` | Get new access token with refresh token  |

| POST | `/logout/`        | (Optional) Blacklist refresh token       |





🔑 Key Points



| Term              | Meaning                                |

| ----------------- | -------------------------------------- |

| JWTAuthentication | DRF class that validates JWT           |

| Access Token      | Short-lived token for requests         |

| Refresh Token     | Long-lived token to renew access token |

| Bearer Token      | Sent in header `Authorization`         |

| IsAuthenticated   | Permission class to protect views      |





🧠 Beginner Mindset



JWT Authentication = “Passport check”

Access token = temporary ID card

Refresh token = renewal card



Every API request passes through DRF’s authentication pipeline like a security checkpoint.



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 Django REST Framework (DRF)



📌 Definition

DRF is a powerful toolkit for building RESTful APIs using Django.

It makes it easy to create web APIs for your Django applications.



📌 Why Use DRF



Handles serialization of Django models to JSON automatically



Provides class-based views for API endpoints



Supports authentication, permissions, and throttling



Offers Browsable API, so you can test endpoints in the browser



🎯 Key Components of DRF



📌 Serializers



Convert Django models or Python objects → JSON for API responses



Validate incoming JSON from clients → save as Django models



Acts as a translator between Django and API



🧾 Data Flow Example



Sending data: Django model → Serializer → JSON → API response



Receiving data: JSON from client → Serializer → validated → saved as Django model



📌 ViewSets \& API Views



Handle API requests: GET, POST, PUT, DELETE



📌 Routers



Automatically generate URL routes for APIs



📌 Authentication \& Permissions



Control who can access API endpoints



🎯 Common Authentication Methods in DRF



1️⃣ Token Authentication



Each user gets a unique token



Send token in Authorization header



Authorization: Token 123456abcdef





Good for simple APIs



2️⃣ Session Authentication



Uses Django sessions (cookies)



Works like normal Django login



Good if frontend \& backend are on the same site



3️⃣ Basic Authentication



Sends username \& password in base64 encoding



Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=





Simple but not secure over plain HTTP → use HTTPS



4️⃣ JWT Authentication



Encode user identity in a secure token



User logs in → gets token → sends in headers for API requests



Authorization: Bearer <your-jwt-token>





5️⃣ OAuth / OAuth2



Used for third-party logins (Google, Facebook)



Complex but secure for social login



🎯 Permission Classes in DRF



1️⃣ AllowAny



Anyone can access endpoint



2️⃣ IsAuthenticated



Only authenticated users (JWT/session) can access



3️⃣ IsAdminUser



Only admin (is\_staff=True) can access



4️⃣ IsAuthenticatedOrReadOnly



Authenticated → Can read \& modify



Unauthenticated → Can only read



5️⃣ Custom Permissions



Subclass BasePermission



🧾 Example: User can edit only their own posts



from rest\_framework.permissions import BasePermission



class IsOwner(BasePermission):

&nbsp;   def has\_object\_permission(self, request, view, obj):

&nbsp;       return obj.owner == request.user



🎯 Django Relationships



1️⃣ One-to-One Relationship



One record belongs to only one other record



🧾 Example



user = models.OneToOneField(User, on\_delete=models.CASCADE)





User ↔️ Profile (1 to 1)



2️⃣ One-to-Many Relationship



One item → many related items



🧾 Example



user = models.ForeignKey(User, on\_delete=models.CASCADE)





User ➝ Post (1 user, many posts)



3️⃣ Many-to-Many Relationship



Many items ↔ many items



🧾 Example



students = models.ManyToManyField(Student)





Students ⇆ Courses



🎯 KYC (Know Your Customer)



📌 Definition

System checks \& verifies who the user is before giving full access



📌 Purpose



Prevent fraud / fake accounts



Stop money laundering



Follow legal regulations



Ensure real human users



🎯 Admin Fieldsets



📌 Purpose



Customize how your model looks in Django Admin forms



🧾 Example: admin.py



from django.contrib import admin

from .models import Student



@admin.register(Student)

class StudentAdmin(admin.ModelAdmin):

&nbsp;   fieldsets = (

&nbsp;       ('Personal Info', {'fields': ('name', 'age', 'email')}),

&nbsp;       ('Course Info', {'fields': ('course', 'enrolled\_date')}),

&nbsp;   )





Organizes form into sections like Personal Info \& Course Info



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End



🎯 DRF Permission Classes (Recap)



1️⃣ AllowAny



Anyone can access the endpoint (authenticated or not)



2️⃣ IsAuthenticated



Only logged-in users (with valid JWT or session) can access



3️⃣ IsAdminUser



Only admin users (is\_staff=True) can access



4️⃣ IsAuthenticatedOrReadOnly



Authenticated users → Can read \& modify



Unauthenticated users → Can only read



5️⃣ Custom Permissions



Subclass BasePermission to create your own rules



🧾 Example of a Custom Permission



from rest\_framework.permissions import BasePermission



class IsOwner(BasePermission):

&nbsp;   def has\_object\_permission(self, request, view, obj):

&nbsp;       return obj.owner == request.user



🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End 🔚 End

























