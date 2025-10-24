a variable is simple a name that refers to an object in memory



datatype is the value stored inside a variable



number one type of datatype in python is intergal and intergal is a number 



string is also a datatype in python



boolean (true/false) is also a datatype in python



In Python, list is a mutable data type, which means you can change 

its content after creating it (add, remove, or modify elements).

\# creating a list

fruits = \["apple", "banana", "cherry"]

print("Original list:", fruits)



\# modifying an element

fruits\[1] = "orange"

print("After modifying:", fruits)



\# adding a new element

fruits.append("mango")

print("After adding:", fruits)



\# removing an element

fruits.remove("apple")

print("After removing:", fruits)





A tuple is an ordered, immutable collection in Python.

Example of a Tuple

\# Creating a tuple

colors = ("red", "green", "blue")

print(colors)

print(type(colors))   # <class 'tuple'>





A set is an unordered, mutable, and unique collection of items in Python.

Example of a Set

fruits = {"apple", "banana", "cherry"}

print(fruits)

print(type(fruits))   # <class 'set'>





So the quick memory trick is:

\[] → list

() → tuple

{} → set (or dict if empty)





a function in python is block of reusable codes



operators in python below:

Arithmetic Operators

Comparison (Relational) Operators

Logical Operators

Assignment Operators

Bitwise Operators

Membership Operators

Identity Operators







Arithmetic Operators

x = 10

y = 3

print(x + y)   # Addition → 13

print(x - y)   # Subtraction → 7

print(x \* y)   # Multiplication → 30

print(x / y)   # Division → 3.333...

print(x // y)  # Floor Division → 3

print(x % y)   # Modulus (remainder) → 1

print(x \*\* y)  # Exponentiation → 1000







Comparison (Relational) Operators

a, b = 5, 10

print(a == b)  # Equal → False

print(a != b)  # Not equal → True

print(a > b)   # Greater than → False

print(a < b)   # Less than → True

print(a >= b)  # Greater or equal → False

print(a <= b)  # Less or equal → True





Logical Operators

Used with boolean values.

x = True

y = False

print(x and y)   # AND → False

print(x or y)    # OR → True

print(not x)     # NOT → False





Assignment Operators

Used to assign values to variables.

a = 5

a += 3   # a = a + 3 → 8

a -= 2   # a = a - 2 → 6

a \*= 2   # a = a \* 2 → 12

a /= 4   # a = a / 4 → 3.0

a %= 2   # a = a % 2 → 1.0

a \*\*= 3  # a = a \*\* 3 → 1.0





Bitwise Operators

Work on binary numbers.

x = 6   # 110 (binary)

y = 3   # 011 (binary)

print(x \& y)   # AND → 2 (010)

print(x | y)   # OR → 7 (111)

print(x ^ y)   # XOR → 5 (101)

print(~x)      # NOT → -7

print(x << 1)  # Left shift → 12 (1100)

print(x >> 1)  # Right shift → 3 (011)





Membership Operators

Check if a value is in a sequence.

fruits = \["apple", "banana"]

print("apple" in fruits)      # True

print("mango" not in fruits)  # True







Identity Operators

Compare memory locations of objects.

a = \[1, 2, 3]

b = a

c = \[1, 2, 3]

print(a is b)      # True (same object in memory)

print(a is c)      # False (different objects, same values)

print(a is not c)  # True





Function Syntax in Python

def function\_name(parameters):

&nbsp;  

&nbsp;   Optional docstring explaining the function

&nbsp;  

&nbsp;   # function body (code to run)

&nbsp;   return value   # optional





Function with Parameters



def greet\_user(name):

&nbsp;   print("Hello,", name)



greet\_user("Alice")











In Python, a function is defined using the def keyword.

Here’s the basic syntax:



Example 1: A simple function without parameters

def greet():

&nbsp;   print("Hello, welcome to Python!")





Example 2: Function with parameters

def add(a, b):

&nbsp;   return a + b







Example 3: Function with default parameter

def greet\_user(name="Guest"):

&nbsp;   print(f"Hello, {name}!")





Parameters are variables listed inside the parentheses of a function definition.  

They act as placeholders for the values (arguments) you pass when calling the function.



oop is a program paradigm  that organize around object rather than just function and 

procedure. oop helps you build reuseable modular coes that are easier to maintain.



excapsulation is one of the pillars of oop, excapsulation is more like building 

parameter and method using into sinle unit and controlling access to them



inheritance is just creating new class base on existing class to reuse codes



polymorphism allowing diffrent class to be treated as instance of the same 

class through a common interface



abstraction it is hiding complex implementation details and exposing only

what is neccessary.





a class in python is a blueprint for creating object

a class define the data and method and object will have



an object in python is an instance of a class 



attribute are variable attach to object or classess

instance attribute are unique to each object and are always define in method

class attribute are attribute shared by all object of a class



**HTTP : hyper text transfer protocol:**



**http methods:**



http method defines the type of action or operation you want to 

perform on a resources



1. **GET METHOD :** its used to retrieve or fetch data from the server without

&nbsp;	modifying . it's commonly used to get data from the server.



2\. **POST METHOD:** it's used to create new resources on the server

&nbsp;	or submit data for processing.



3\. **PUT METHOD:** it's used to update or replace an entire existing resources

&nbsp;	with new data.



4\. **DELETE METHOD :**  it's used to remove a resources from the server



5\. **PATCH METHOD:** it's used for partial update to resources modifying

&nbsp;	only specific things without replacing all the resources.



6\. **HEAD METHOD:**  it's used like **GET**  but it retrieves only headers



7\. **OPTIONS METHOD:** it describes the communication option for a resources 





			**HTTP STATUS CODE BELOW** 

status code are the three digits numbers in responses indicating the

result of the request.



1. 1xx: it means you are passing an information
2. 2xx : \[ 201,202] : it's all about success 
3. 3xx : \[ 300,301] : you are being redirected
4. 4xx: \[400,4001] : error from the front end
5. 5xx: \[ 500, 5001 ] : server error from the backend 





&nbsp;			**COMMON STATUS BELOW**



1. 200: means ok or successful
2. 201: means created
3. 204: means you're passing a data and you are expecting nothing
4. 301: means moved permanently
5. 302: temporary redirection
6. 400: bad requests 
7. 401: unauthorized 
8. 403: access denied
9. 404: resources does not exist
10. 500: server error 
11. 502: invalid responses from offspring server
12. 503: temporarily overloaded or down



			**DATA BASE**





Data base is a structured place where we store, organize and manage data



			**THINGS YOU NEED TO KNOW :**



* relational database : they store data in tables e.g MySQL, Postre.sql , SQLite
* non relational database: they are stored in document, key value pair or collection

&nbsp;   and they are used when you are not dealing with much data and they are used for 

&nbsp;   small scale projects e.g mongodb, firebase and Cassandra.





			**BASIC OPERATION IN DATABASE :**



1. Crud operation: crud stands for " create, read, update and delete"

* create is used to add new data
* readd is used for reading user-data
* update is used for changing data
* delete is used for for removing dat





			**concept of database**



* skimmer: define how a data is organize 
* tables and collection
* record 
* primary key
* foreign key



			**type of field:**



charfield

textfield

emailfield

url filed

slug field

uuid field 

int field 

small int field

big int field

float field

decimal field

date field

time field

date and time field

duration field

Boolean field

non-Boolean field

foreign key 

one to one field

many to many field

file field





			**JSON CONCEPT**



&nbsp;it's a lightweight data format the we can easily use and write\[ javascript object Notation\[ JSON] ] 



&nbsp;			**JSON STRUCTURE**



it has the structure of a dictionary and it follows the concept of a key-value pair



**there are two ways to build a full-stack project**



1. we can either use python , flask or django template
2. and use of API





 			**MOST COMMNON WAYS TO USE JSON DATA**



1. JSON.dump(object) : to convert python object to JSON string
2. JSON.loads(object): converting JSON string to python object
3. JSON.dump(object, file) : to convert python object to JSON string then to a particular file
4. JSON.load(file) : if you want to convert JSON string to python object in a particular file





&nbsp;			**REST API**

what is  REST API? in python is known as representational state transfer , it is also an 

architectural style for designing network application  often used for API and it is 

stateless ( it carries all information the client needs ) 

stateless means all user get it unique call of the API request and response and used

for authentication.

























