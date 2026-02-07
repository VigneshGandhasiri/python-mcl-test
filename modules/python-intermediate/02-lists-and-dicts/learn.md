# Lists and Dictionaries in Python

In this final topic, you'll learn about two of Python's most powerful and commonly used data structures: lists and dictionaries. These allow you to store, organize, and manipulate collections of data efficiently.

## What are Data Structures?

Data structures are ways to organize and store data. Lists and dictionaries are built-in Python data structures that help you work with multiple values in a single variable.

## Lists

A list is an ordered collection of items. Lists can contain any type of data and can be modified after creation.

### Creating Lists

```python
# Empty list
empty_list = []

# List of numbers
numbers = [1, 2, 3, 4, 5]

# List of strings
fruits = ["apple", "banana", "orange"]

# Mixed types
mixed = [1, "hello", 3.14, True]

# Nested lists
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

print(numbers)
# Output: [1, 2, 3, 4, 5]
```

### Accessing List Elements

Lists use zero-based indexing (first element is at index 0).

```python
fruits = ["apple", "banana", "orange", "mango"]

# Positive indexing
print(fruits[0])
# Output: apple

print(fruits[2])
# Output: orange

# Negative indexing (from the end)
print(fruits[-1])
# Output: mango

print(fruits[-2])
# Output: orange
```

### List Slicing

Extract portions of a list using slicing.

```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Basic slicing [start:stop]
print(numbers[2:5])
# Output: [2, 3, 4]

# From start to index
print(numbers[:4])
# Output: [0, 1, 2, 3]

# From index to end
print(numbers[6:])
# Output: [6, 7, 8, 9]

# With step [start:stop:step]
print(numbers[::2])
# Output: [0, 2, 4, 6, 8]

# Reverse a list
print(numbers[::-1])
# Output: [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
```

### Modifying Lists

Lists are mutable - you can change their contents.

```python
fruits = ["apple", "banana", "orange"]

# Change an element
fruits[1] = "grape"
print(fruits)
# Output: ['apple', 'grape', 'orange']

# Add elements
fruits.append("mango")
print(fruits)
# Output: ['apple', 'grape', 'orange', 'mango']

# Insert at specific position
fruits.insert(1, "kiwi")
print(fruits)
# Output: ['apple', 'kiwi', 'grape', 'orange', 'mango']

# Remove elements
fruits.remove("grape")
print(fruits)
# Output: ['apple', 'kiwi', 'orange', 'mango']

# Remove by index
popped = fruits.pop(1)
print(f"Removed: {popped}")
# Output: Removed: kiwi

print(fruits)
# Output: ['apple', 'orange', 'mango']
```

### Common List Methods

| Method | Description | Example |
|--------|-------------|---------|
| `append(item)` | Add item to end | `list.append(5)` |
| `insert(index, item)` | Insert at position | `list.insert(0, 'first')` |
| `remove(item)` | Remove first occurrence | `list.remove('apple')` |
| `pop(index)` | Remove and return item | `list.pop(0)` |
| `clear()` | Remove all items | `list.clear()` |
| `sort()` | Sort in place | `list.sort()` |
| `reverse()` | Reverse in place | `list.reverse()` |
| `count(item)` | Count occurrences | `list.count(5)` |
| `index(item)` | Find index of item | `list.index('apple')` |
| `extend(list2)` | Add all items from list2 | `list.extend([1,2,3])` |

### List Operations

```python
# Concatenation
list1 = [1, 2, 3]
list2 = [4, 5, 6]
combined = list1 + list2
print(combined)
# Output: [1, 2, 3, 4, 5, 6]

# Repetition
repeated = [0] * 5
print(repeated)
# Output: [0, 0, 0, 0, 0]

# Membership testing
fruits = ["apple", "banana", "orange"]
print("apple" in fruits)
# Output: True

print("grape" in fruits)
# Output: False

# Length
print(len(fruits))
# Output: 3

# Min, Max, Sum (for numeric lists)
numbers = [5, 2, 8, 1, 9]
print(f"Min: {min(numbers)}, Max: {max(numbers)}, Sum: {sum(numbers)}")
# Output: Min: 1, Max: 9, Sum: 25
```

### Iterating Through Lists

```python
fruits = ["apple", "banana", "orange"]

# Basic iteration
for fruit in fruits:
    print(fruit)

# Iteration with index
for i in range(len(fruits)):
    print(f"{i}: {fruits[i]}")

# Using enumerate()
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
# Output:
# 0: apple
# 1: banana
# 2: orange
```

### List Comprehensions

A concise way to create lists.

```python
# Create list of squares
squares = [x ** 2 for x in range(1, 6)]
print(squares)
# Output: [1, 4, 9, 16, 25]

# Filter even numbers
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evens = [x for x in numbers if x % 2 == 0]
print(evens)
# Output: [2, 4, 6, 8, 10]

# Transform strings
fruits = ["apple", "banana", "orange"]
uppercase = [fruit.upper() for fruit in fruits]
print(uppercase)
# Output: ['APPLE', 'BANANA', 'ORANGE']
```

## Dictionaries

A dictionary is an unordered collection of key-value pairs. Each key must be unique and maps to a value.

### Creating Dictionaries

```python
# Empty dictionary
empty_dict = {}

# Dictionary with initial values
student = {
    "name": "Alice",
    "age": 20,
    "grade": "A"
}

# Using dict() constructor
person = dict(name="Bob", age=25, city="New York")

print(student)
# Output: {'name': 'Alice', 'age': 20, 'grade': 'A'}
```

### Accessing Dictionary Values

```python
student = {
    "name": "Alice",
    "age": 20,
    "grade": "A"
}

# Access using key
print(student["name"])
# Output: Alice

# Using get() method (safer - returns None if key doesn't exist)
print(student.get("age"))
# Output: 20

print(student.get("phone"))
# Output: None

# Default value with get()
print(student.get("phone", "Not available"))
# Output: Not available
```

### Modifying Dictionaries

```python
student = {
    "name": "Alice",
    "age": 20,
    "grade": "A"
}

# Update existing value
student["age"] = 21
print(student)
# Output: {'name': 'Alice', 'age': 21, 'grade': 'A'}

# Add new key-value pair
student["phone"] = "555-1234"
print(student)
# Output: {'name': 'Alice', 'age': 21, 'grade': 'A', 'phone': '555-1234'}

# Remove key-value pair
del student["phone"]
print(student)
# Output: {'name': 'Alice', 'age': 21, 'grade': 'A'}

# Remove and return value
grade = student.pop("grade")
print(f"Removed grade: {grade}")
# Output: Removed grade: A
```

### Common Dictionary Methods

| Method | Description | Example |
|--------|-------------|---------|
| `get(key, default)` | Get value safely | `dict.get('name', 'Unknown')` |
| `keys()` | Get all keys | `dict.keys()` |
| `values()` | Get all values | `dict.values()` |
| `items()` | Get key-value pairs | `dict.items()` |
| `pop(key)` | Remove and return value | `dict.pop('name')` |
| `clear()` | Remove all items | `dict.clear()` |
| `update(dict2)` | Update with another dict | `dict.update(other)` |

### Iterating Through Dictionaries

```python
student = {
    "name": "Alice",
    "age": 20,
    "grade": "A"
}

# Iterate over keys
for key in student:
    print(key)
# Output: name, age, grade

# Iterate over values
for value in student.values():
    print(value)
# Output: Alice, 20, A

# Iterate over key-value pairs
for key, value in student.items():
    print(f"{key}: {value}")
# Output:
# name: Alice
# age: 20
# grade: A
```

### Nested Dictionaries

```python
# Dictionary of dictionaries
students = {
    "student1": {
        "name": "Alice",
        "age": 20,
        "grade": "A"
    },
    "student2": {
        "name": "Bob",
        "age": 22,
        "grade": "B"
    }
}

# Access nested values
print(students["student1"]["name"])
# Output: Alice

# Iterate through nested structure
for student_id, info in students.items():
    print(f"{student_id}:")
    for key, value in info.items():
        print(f"  {key}: {value}")
```

### Dictionary Comprehensions

```python
# Create dictionary from lists
keys = ["name", "age", "city"]
values = ["Alice", 25, "NYC"]
person = {k: v for k, v in zip(keys, values)}
print(person)
# Output: {'name': 'Alice', 'age': 25, 'city': 'NYC'}

# Transform dictionary
prices = {"apple": 1.0, "banana": 0.5, "orange": 0.75}
discounted = {item: price * 0.9 for item, price in prices.items()}
print(discounted)
# Output: {'apple': 0.9, 'banana': 0.45, 'orange': 0.675}

# Filter dictionary
scores = {"Alice": 85, "Bob": 92, "Charlie": 78, "Diana": 95}
high_scores = {name: score for name, score in scores.items() if score >= 90}
print(high_scores)
# Output: {'Bob': 92, 'Diana': 95}
```

## Comparing Lists and Dictionaries

| Feature | List | Dictionary |
|---------|------|------------|
| **Ordering** | Ordered | Unordered (Python 3.7+ maintains insertion order) |
| **Access** | By index (0, 1, 2...) | By key |
| **Duplicates** | Allowed | Keys must be unique |
| **Mutability** | Mutable | Mutable |
| **Use Case** | Sequential data | Key-value mappings |

## Practical Examples

### Example 1: Student Grade Management

```python
# List of student dictionaries
students = [
    {"name": "Alice", "score": 85},
    {"name": "Bob", "score": 92},
    {"name": "Charlie", "score": 78}
]

# Calculate average score
total = sum(student["score"] for student in students)
average = total / len(students)
print(f"Average score: {average:.2f}")
# Output: Average score: 85.00

# Find top student
top_student = max(students, key=lambda s: s["score"])
print(f"Top student: {top_student['name']} with score {top_student['score']}")
# Output: Top student: Bob with score 92
```

### Example 2: Word Frequency Counter

```python
text = "hello world hello python world"
words = text.split()

# Count word frequency
frequency = {}
for word in words:
    if word in frequency:
        frequency[word] += 1
    else:
        frequency[word] = 1

print(frequency)
# Output: {'hello': 2, 'world': 2, 'python': 1}

# Alternative using get()
frequency2 = {}
for word in words:
    frequency2[word] = frequency2.get(word, 0) + 1

print(frequency2)
# Output: {'hello': 2, 'world': 2, 'python': 1}
```

### Example 3: Shopping Cart

```python
# Cart as list of dictionaries
cart = [
    {"item": "apple", "price": 1.0, "quantity": 3},
    {"item": "banana", "price": 0.5, "quantity": 5},
    {"item": "orange", "price": 0.75, "quantity": 4}
]

# Calculate total
total = sum(item["price"] * item["quantity"] for item in cart)
print(f"Total: ${total:.2f}")
# Output: Total: $8.50
```

## Practice Exercises

Before taking the quiz, try these exercises:

1. Create a list of numbers and find all numbers greater than 5
2. Write a program that removes duplicates from a list
3. Create a dictionary to store phone numbers and add/remove entries
4. Merge two dictionaries into one
5. Create a list of dictionaries representing a book library with title, author, and year

## Key Takeaways

- **Lists** store ordered collections accessible by index
- **List methods** include append, insert, remove, pop, sort
- **List slicing** extracts portions of lists
- **List comprehensions** create lists concisely
- **Dictionaries** store key-value pairs
- **Dictionary methods** include get, keys, values, items
- **Nested structures** combine lists and dictionaries
- **Comprehensions** work for both lists and dictionaries

Lists and dictionaries are fundamental to Python programming. They're used extensively in real-world applications for data storage, manipulation, and organization!

## Congratulations!

You've completed the Python Intermediate module! You now have a solid foundation in:
- Basic operators and expressions
- Conditional statements
- Loops and iteration
- Functions and code organization
- Lists and dictionaries for data management

These skills prepare you for more advanced Python topics like object-oriented programming, file handling, and working with external libraries. Keep practicing and building projects to reinforce your learning!
