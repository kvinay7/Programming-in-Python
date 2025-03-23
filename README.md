# [Programming in Python](https://github.com/kvinay7/Programming-in-Python/blob/main/Programming%20in%20Python.docx)
Python is a high-level, interpreted programming language known for its simplicity and readability. It is widely used in web development, data science, artificial intelligence (AI), machine learning (ML), automation, and scripting.

## 🔹 **How This is Different from C or Java?**  
| Feature | Python (Interpreted) | Java (Bytecode + JVM) | C (Compiled) |
|---------|----------------------|----------------------|-------------|
| Compilation | Compiled to bytecode automatically at runtime | Compiled to bytecode (`.class` files) | Compiled to machine code (`.exe`, `.out`) |
| Execution | Bytecode runs on Python Virtual Machine (PVM) | Bytecode runs on Java Virtual Machine (JVM) | Runs directly on CPU |
| Portability | Runs on any OS with Python installed | Runs on any OS with JVM installed | Needs recompilation for different OS |
| Speed | Slower (interpreted at runtime) | Faster than Python | Fastest (direct machine code execution) |
- Python variables don’t need type declarations. Has mutable (list, dict, set) & immutable (numeric, tuple, string) types.
---

<details>
  <summary><h2>Functions in Python</h2></summary>

  A **function** is a reusable block of code that performs a specific task. Python provides **built-in functions** (e.g., `print()`, `len()`, `sum()`) and allows users to create **custom functions**.

### **1️⃣ Defining and Calling Functions**  
#### **🔹 Basic Function**
```python
def greet():
    print("Hello, World!")

greet()  # Output: Hello, World!
```
✅ Use `def` keyword to define a function.  
✅ Call the function using its name followed by `()`.  

---

### **2️⃣ Function Parameters and Arguments**
#### **🔹 Function with Parameters**
```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # Output: Hello, Alice!
```
✅ Parameters are **placeholders** inside function definitions.  
✅ Arguments are **actual values** passed to the function.  

---

#### **🔹 Default Parameter Values**
```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()        # Output: Hello, Guest!
greet("Bob")   # Output: Hello, Bob!
```
✅ If no argument is provided, the **default value is used**.  

---

#### **🔹 Return Statement**
```python
def add(a, b):
    return a + b

result = add(5, 3)
print(result)  # Output: 8
```
✅ **`return`** sends a result back to the caller.  
✅ Functions without `return` return `None` by default.  

---

### **3️⃣ Types of Function Arguments**
Python allows **different types of arguments** for flexibility.  

#### **🔹 1. Positional Arguments**  
Values are assigned based on their **position**.  
```python
def describe_pet(name, species):
    print(f"{name} is a {species}")

describe_pet("Buddy", "dog")  # Output: Buddy is a dog
```

---

#### **🔹 2. Keyword Arguments**
Arguments are passed using **key=value** pairs.  
```python
describe_pet(species="cat", name="Whiskers")  
# Output: Whiskers is a cat
```
✅ Order **does not matter** in keyword arguments.  

---

#### **🔹 3. Arbitrary Arguments (`*args`)**
Used when the number of arguments is **unknown**.  
```python
def sum_numbers(*numbers):
    return sum(numbers)

print(sum_numbers(1, 2, 3, 4))  # Output: 10
```
✅ `*args` collects **multiple arguments** into a **tuple**.  

---

#### **🔹 4. Arbitrary Keyword Arguments (`**kwargs`)**
Used when the number of **keyword arguments** is **unknown**.  
```python
def display_info(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

display_info(name="Alice", age=25, city="New York")
```
✅ `**kwargs` collects multiple **keyword arguments** into a **dictionary**.  

---

### **4️⃣ Lambda (Anonymous) Functions**
Lambda functions are **one-liner** functions used for **small operations**.  

```python
# Regular Function
def square(x):
    return x * x

# Lambda Function
square = lambda x: x * x

print(square(5))  # Output: 25
```
✅ **No `def`, just `lambda parameters: expression`**.  
✅ Used in **sorting, filtering, and functional programming**.  

---

### **5️⃣ Higher-Order Functions**
Functions that take **other functions as arguments**.

#### **🔹 `map()` – Apply Function to Each Item**
```python
numbers = [1, 2, 3, 4]
squared = list(map(lambda x: x * x, numbers))
print(squared)  # Output: [1, 4, 9, 16]
```
✅ `map()` applies a function to **each element** of a sequence.  

---

#### **🔹 `filter()` – Filter Elements Based on Condition**
```python
numbers = [1, 2, 3, 4, 5, 6]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # Output: [2, 4, 6]
```
✅ `filter()` keeps only the **True** values.  

---

### **6️⃣ Nested & Recursive Functions**
#### **🔹 Nested Functions**
A function inside another function.  
```python
def outer():
    def inner():
        print("Hello from inner function!")
    inner()

outer()
```
✅ **Inner function** can only be called inside **outer function**.  

---

#### **🔹 Recursive Functions**
A function **calls itself** for problems like factorial, Fibonacci, etc.  
```python
def factorial(n):
    if n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))  # Output: 120
```
✅ Recursion helps in **divide-and-conquer problems**.  

---

### **7️⃣ Function Decorators (Advanced)**
Decorators modify function behavior **without changing the function itself**.

```python
def decorator(func):
    def wrapper():
        print("Before function call")
        func()
        print("After function call")
    return wrapper

@decorator
def say_hello():
    print("Hello!")

say_hello()
```
✅ `@decorator` is **syntactic sugar** for `say_hello = decorator(say_hello)`.  

---
</details>

<details>
  <summary><h2>Exception Handling in Python</h2></summary>

### **1️⃣ What is Exception Handling?**
Exception handling in Python allows us to **gracefully handle errors** instead of abruptly stopping the program. This is done using `try-except` blocks.

### **2️⃣ Basic `try-except` Example**
```python
try:
    x = 5 / 0  # Division by zero
except ZeroDivisionError:
    print("Cannot divide by zero!")
```
✅ **`try` block** contains the code that may raise an exception.  
✅ **`except` block** handles the error gracefully.  

**🔹 Output:**  
```
Cannot divide by zero!
```

---

### **3️⃣ Handling Multiple Exceptions**
```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError:
    print("You cannot divide by zero!")
except ValueError:
    print("Invalid input! Please enter a number.")
```
✅ Multiple `except` blocks can handle **different types of exceptions**.

---

### **4️⃣ Catching Multiple Exceptions in One Block**
```python
try:
    x = int("abc")  # Causes ValueError
except (ValueError, TypeError) as e:
    print(f"An error occurred: {e}")
```
✅ Use a tuple `(Error1, Error2)` to catch **multiple exceptions in one block**.

---

### **5️⃣ Using `else` Block (Runs if No Exception Occurs)**
```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError:
    print("You cannot divide by zero!")
else:
    print(f"Result: {result}")  # Runs if no error occurs
```
✅ The `else` block **executes only if no exception occurs**.

---

### **6️⃣ Using `finally` Block (Always Executes)**
```python
try:
    file = open("test.txt", "r")
    content = file.read()
except FileNotFoundError:
    print("File not found!")
finally:
    print("Execution completed!")  # Always runs
```
✅ The `finally` block **always executes** (even if an exception occurs).  
✅ Used for **cleanup operations** like closing files.

---

### **7️⃣ Raising Custom Exceptions (`raise`)**
```python
def check_age(age):
    if age < 18:
        raise ValueError("Age must be 18 or above")
    print("You are eligible.")

try:
    check_age(16)
except ValueError as e:
    print(e)
```
✅ **`raise`** is used to **manually trigger an exception**.

---

### **8️⃣ Creating Custom Exceptions**
```python
class MyException(Exception):
    pass  # Custom exception class

try:
    raise MyException("Something went wrong!")
except MyException as e:
    print(e)
```
✅ You can **define your own exception classes** by inheriting from `Exception`.

---
</details>

<details>
  <summary><h1>Object-Oriented Programming (OOP) in Python</h1></summary>

**Object-Oriented Programming (OOP)** is a programming paradigm that models real-world entities using **classes** and **objects**. Python supports OOP with key principles like **Encapsulation, Inheritance, Polymorphism, and Abstraction**.

---

## **1️⃣ Classes & Objects in Python** 

```python
# Defining a Class
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def display_info(self):
        print(f"Car: {self.brand} {self.model}")

# Creating Objects
car1 = Car("Toyota", "Corolla")
car2 = Car("Honda", "Civic")

# Accessing Methods
car1.display_info()  # Output: Car: Toyota Corolla
car2.display_info()  # Output: Car: Honda Civic
```

✅ **`__init__`** is the **constructor** that initializes object attributes.  
✅ **`self`** represents the instance of the class.  

---

## **2️⃣ OOP Pillars in Python**

### **🔹 1. Encapsulation (Data Hiding)**
- Protects data using **private variables** (`__variable`).

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance  # Private variable

    def deposit(self, amount):
        self.__balance += amount

    def get_balance(self):
        return self.__balance

account = BankAccount(1000)
account.deposit(500)
print(account.get_balance())  # Output: 1500
# print(account.__balance)  # Error: Cannot access private variable
```
✅ Use `__variable` to **hide** attributes.  
✅ Provide **getter/setter** methods for controlled access.  

---

### **🔹 2. Inheritance (Code Reusability)**
- A class can **inherit** attributes & methods from another class.

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):  # Dog inherits Animal
    def speak(self):
        print("Dog barks")

dog = Dog()
dog.speak()  # Output: Dog barks
```
✅ **Child class (`Dog`) inherits from Parent class (`Animal`)**.  
✅ **Method Overriding** allows modifying behavior.  

---

### **🔹 3. Polymorphism (Multiple Forms)**
- **Method Overriding:** Redefining a method in a child class.

```python
class Bird:
    def sound(self):
        print("Chirping")

class Parrot(Bird):
    def sound(self):
        print("Parrot is talking")

obj = Parrot()
obj.sound()  # Output: Parrot is talking
```

- **Method Overloading** is **not directly supported** but can be simulated using **default arguments**.

```python
class Math:
    def add(self, a, b, c=0):
        return a + b + c

m = Math()
print(m.add(2, 3))       # Output: 5
print(m.add(2, 3, 4))    # Output: 9
```

✅ **Same method name but different behaviors**.  

---

### **🔹 4. Abstraction (Hiding Implementation)**
- Achieved using **abstract classes** (`ABC` module).

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):  # Abstract Class
    @abstractmethod
    def start(self):
        pass  # Abstract Method

class Car(Vehicle):
    def start(self):
        print("Car is starting")

c = Car()
c.start()  # Output: Car is starting
```
✅ **Hides implementation details** and **enforces method implementation** in child classes.  

---

## **3️⃣ Special OOP Features in Python**
### **🔹 1. `super()` - Call Parent Class Constructor**
```python
class Parent:
    def __init__(self):
        print("Parent Constructor")

class Child(Parent):
    def __init__(self):
        super().__init__()  # Calls Parent Constructor
        print("Child Constructor")

c = Child()
# Output:
# Parent Constructor
# Child Constructor
```

---

### **🔹 2. Operator Overloading (`__add__`, `__str__`)**
- Allows **customizing built-in operators** for objects.

```python
class Book:
    def __init__(self, pages):
        self.pages = pages

    def __add__(self, other):
        return self.pages + other.pages  # Overload + operator

book1 = Book(300)
book2 = Book(200)

print(book1 + book2)  # Output: 500
```

---

### **🔹 3. Multiple Inheritance**
- A class can inherit from **multiple parent classes**.

```python
class A:
    def show(self):
        print("Class A")

class B:
    def display(self):
        print("Class B")

class C(A, B):
    pass

obj = C()
obj.show()     # Output: Class A
obj.display()  # Output: Class B
```

✅ Supports multiple inheritance but can lead to **complexity** (use wisely).  

---
</details>
