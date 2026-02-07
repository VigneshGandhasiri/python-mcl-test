# Functions in Python

Welcome to the intermediate level! Functions are one of the most important concepts in Python programming. They help you organize code, avoid repetition, and make your programs more maintainable.

## What are Functions?

A function is a reusable block of code that performs a specific task. Instead of writing the same code multiple times, you write it once in a function and call it whenever needed.

Think of functions like a recipe - you define the steps once, then follow the recipe whenever you want to make that dish!

## Why Use Functions?

| Benefit | Description |
|---------|-------------|
| **Reusability** | Write once, use many times |
| **Organization** | Break complex problems into smaller parts |
| **Readability** | Code becomes easier to understand |
| **Maintainability** | Fix bugs in one place, not everywhere |
| **Testing** | Test individual functions separately |

## Defining a Function

Use the `def` keyword to define a function.

### Basic Syntax:

```python
def function_name():
    # function body
    # code to execute
```

### Examples:

```python
# Simple function with no parameters
def greet():
    print("Hello, World!")

# Call the function
greet()
# Output: Hello, World!

# Function with multiple statements
def introduce():
    print("Welcome to Python!")
    print("Functions make coding easier")
    print("Let's learn together!")

introduce()
# Output:
# Welcome to Python!
# Functions make coding easier
# Let's learn together!
```

## Functions with Parameters

Parameters allow you to pass data to functions, making them more flexible.

### Syntax:

```python
def function_name(parameter1, parameter2):
    # use parameters in function body
```

### Examples:

```python
# Function with one parameter
def greet_person(name):
    print(f"Hello, {name}!")

greet_person("Alice")
# Output: Hello, Alice!

greet_person("Bob")
# Output: Hello, Bob!

# Function with multiple parameters
def add_numbers(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")

add_numbers(5, 3)
# Output: 5 + 3 = 8

add_numbers(10, 20)
# Output: 10 + 20 = 30
```

## Return Values

Functions can return values using the `return` statement. This allows you to use the result elsewhere in your code.

### Examples:

```python
# Function that returns a value
def square(number):
    return number ** 2

result = square(5)
print(result)
# Output: 25

# Use returned value in expression
print(square(3) + square(4))
# Output: 25 (9 + 16)

# Function with multiple calculations
def calculate_area(length, width):
    area = length * width
    return area

room_area = calculate_area(10, 8)
print(f"Room area: {room_area} square meters")
# Output: Room area: 80 square meters
```

### Returning Multiple Values:

```python
# Return multiple values as a tuple
def get_min_max(numbers):
    minimum = min(numbers)
    maximum = max(numbers)
    return minimum, maximum

nums = [5, 2, 9, 1, 7]
min_val, max_val = get_min_max(nums)

print(f"Min: {min_val}, Max: {max_val}")
# Output: Min: 1, Max: 9

# Return multiple values with different types
def analyze_text(text):
    length = len(text)
    uppercase = text.upper()
    word_count = len(text.split())
    return length, uppercase, word_count

char_count, upper_text, words = analyze_text("Hello World")
print(f"Characters: {char_count}, Words: {words}")
# Output: Characters: 11, Words: 2
```

## Default Parameters

You can provide default values for parameters. If no value is passed, the default is used.

### Examples:

```python
# Function with default parameter
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet("Alice")
# Output: Hello, Alice!

greet()
# Output: Hello, Guest!

# Multiple default parameters
def power(base, exponent=2):
    return base ** exponent

print(power(5))
# Output: 25 (5^2, using default exponent)

print(power(5, 3))
# Output: 125 (5^3, custom exponent)

# Function with multiple defaults
def create_profile(name, age=0, country="Unknown"):
    print(f"Name: {name}")
    print(f"Age: {age}")
    print(f"Country: {country}")

create_profile("Alice", 25, "USA")
# Output: Name: Alice, Age: 25, Country: USA

create_profile("Bob")
# Output: Name: Bob, Age: 0, Country: Unknown
```

## Keyword Arguments

You can pass arguments by parameter name, which makes code more readable and allows you to skip parameters with defaults.

### Examples:

```python
def book_ticket(name, seat, meal="Vegetarian", priority=False):
    print(f"Booking for: {name}")
    print(f"Seat: {seat}")
    print(f"Meal: {meal}")
    print(f"Priority: {priority}")

# Using keyword arguments
book_ticket(name="Alice", seat="12A", meal="Non-veg", priority=True)

# Mix positional and keyword arguments
book_ticket("Bob", "15B", priority=True)

# Skip middle parameters
book_ticket("Charlie", "20C", priority=True)
```

## Variable Number of Arguments

Python allows functions to accept any number of arguments using `*args` and `**kwargs`.

### *args - Variable Positional Arguments:

```python
# Accept any number of arguments
def sum_all(*numbers):
    total = 0
    for num in numbers:
        total += num
    return total

print(sum_all(1, 2, 3))
# Output: 6

print(sum_all(10, 20, 30, 40, 50))
# Output: 150

# Function that prints all items
def print_items(*items):
    for item in items:
        print(f"- {item}")

print_items("apple", "banana", "orange")
# Output:
# - apple
# - banana
# - orange
```

### **kwargs - Variable Keyword Arguments:

```python
# Accept any number of keyword arguments
def print_info(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=25, city="New York")
# Output:
# name: Alice
# age: 25
# city: New York

# Combine with regular parameters
def create_user(username, **details):
    print(f"Username: {username}")
    for key, value in details.items():
        print(f"{key}: {value}")

create_user("alice123", email="alice@example.com", age=25, country="USA")
```

## Scope of Variables

Variables have different scopes depending on where they're defined.

### Local vs Global Variables:

```python
# Global variable
x = 10

def my_function():
    # Local variable
    y = 5
    print(f"Inside function: x={x}, y={y}")

my_function()
# Output: Inside function: x=10, y=5

print(f"Outside function: x={x}")
# Output: Outside function: x=10

# print(y)  # This would cause an error - y is local to my_function

# Modifying global variable
count = 0

def increment():
    global count  # Declare we're using global variable
    count += 1
    print(f"Count: {count}")

increment()
# Output: Count: 1

increment()
# Output: Count: 2
```

## Lambda Functions

Lambda functions are small, anonymous functions defined in a single line.

### Syntax:

```python
lambda arguments: expression
```

### Examples:

```python
# Regular function
def square(x):
    return x ** 2

# Equivalent lambda function
square_lambda = lambda x: x ** 2

print(square(5))
# Output: 25

print(square_lambda(5))
# Output: 25

# Lambda with multiple arguments
multiply = lambda x, y: x * y
print(multiply(3, 4))
# Output: 12

# Using lambda with built-in functions
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))
print(squared)
# Output: [1, 4, 9, 16, 25]

# Sort using lambda
students = [("Alice", 85), ("Bob", 92), ("Charlie", 78)]
students.sort(key=lambda student: student[1])
print(students)
# Output: [('Charlie', 78), ('Alice', 85), ('Bob', 92)]
```

## Docstrings

Docstrings are documentation strings that describe what a function does.

### Examples:

```python
def calculate_bmi(weight, height):
    """
    Calculate Body Mass Index (BMI).
    
    Parameters:
    weight (float): Weight in kilograms
    height (float): Height in meters
    
    Returns:
    float: BMI value
    """
    return weight / (height ** 2)

# Access docstring
print(calculate_bmi.__doc__)

# Use the function
bmi = calculate_bmi(70, 1.75)
print(f"BMI: {bmi:.2f}")
# Output: BMI: 22.86
```

## Common Function Patterns

### Pattern 1: Validation Function

```python
def is_valid_email(email):
    return "@" in email and "." in email

print(is_valid_email("user@example.com"))
# Output: True

print(is_valid_email("invalid-email"))
# Output: False
```

### Pattern 2: Calculation Function

```python
def calculate_discount(price, discount_percent):
    discount = price * (discount_percent / 100)
    final_price = price - discount
    return final_price

print(calculate_discount(100, 20))
# Output: 80.0
```

### Pattern 3: Helper Function

```python
def is_even(number):
    return number % 2 == 0

def filter_even_numbers(numbers):
    result = []
    for num in numbers:
        if is_even(num):
            result.append(num)
    return result

nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_nums = filter_even_numbers(nums)
print(even_nums)
# Output: [2, 4, 6, 8, 10]
```

## Practice Exercises

Before taking the quiz, try these exercises:

1. Create a function that converts Celsius to Fahrenheit
2. Write a function that checks if a number is prime
3. Create a function that reverses a string
4. Write a function that finds the largest number in a list
5. Create a function with default parameters for calculating rectangle area (default width=1)

## Key Takeaways

- **Functions** organize code into reusable blocks
- **Parameters** make functions flexible and dynamic
- **Return values** allow functions to produce results
- **Default parameters** provide fallback values
- **Keyword arguments** improve code readability
- **`*args` and `**kwargs`** handle variable arguments
- **Scope** determines where variables are accessible
- **Lambda functions** create quick, inline functions
- **Docstrings** document function purpose and usage

Functions are the building blocks of well-organized Python programs. They make your code cleaner, more maintainable, and easier to test!

## What's Next?

In the next topic, you'll learn about **Lists and Dictionaries** - Python's most powerful data structures for storing and organizing collections of data. You'll use functions to work with these structures!
