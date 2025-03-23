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

## 🔹 **Functions in Python**  
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

