# Loops in Python

Welcome to loops! Loops are one of the most powerful features in programming. They allow you to repeat code multiple times without writing the same code over and over.

## What are Loops?

Loops let you execute a block of code repeatedly. Instead of writing the same code 100 times, you can use a loop to run it 100 times automatically!

## Types of Loops in Python

Python has two main types of loops:
1. **for loops** - iterate over a sequence
2. **while loops** - repeat while a condition is True

## The for Loop

The `for` loop is used to iterate over a sequence (like a list, string, or range of numbers).

### Basic Syntax:

```python
for variable in sequence:
    # code to repeat
```

### Examples with range():

The `range()` function generates a sequence of numbers.

```python
# Print numbers 0 to 4
for i in range(5):
    print(i)
# Output:
# 0
# 1
# 2
# 3
# 4

# Print numbers 1 to 5
for i in range(1, 6):
    print(i)
# Output: 1, 2, 3, 4, 5

# Print even numbers from 0 to 10
for i in range(0, 11, 2):
    print(i)
# Output: 0, 2, 4, 6, 8, 10
```

### range() Parameters:

| Syntax | Description | Example |
|--------|-------------|---------|
| `range(stop)` | 0 to stop-1 | `range(5)` → 0,1,2,3,4 |
| `range(start, stop)` | start to stop-1 | `range(2, 5)` → 2,3,4 |
| `range(start, stop, step)` | start to stop-1, increment by step | `range(0, 10, 2)` → 0,2,4,6,8 |

### Looping Through Strings:

```python
# Iterate over each character
word = "Python"
for letter in word:
    print(letter)
# Output: P, y, t, h, o, n (each on new line)

# Count vowels in a word
word = "programming"
vowel_count = 0

for letter in word:
    if letter in "aeiou":
        vowel_count += 1

print(f"Number of vowels: {vowel_count}")
# Output: Number of vowels: 3
```

### Looping Through Lists:

```python
# Iterate over list items
fruits = ["apple", "banana", "orange"]

for fruit in fruits:
    print(fruit)
# Output:
# apple
# banana
# orange

# Calculate sum of numbers
numbers = [10, 20, 30, 40, 50]
total = 0

for num in numbers:
    total += num

print(f"Total: {total}")
# Output: Total: 150
```

## The while Loop

The `while` loop repeats code as long as a condition is `True`. Be careful - if the condition never becomes `False`, you'll create an infinite loop!

### Basic Syntax:

```python
while condition:
    # code to repeat
    # update condition to eventually make it False
```

### Examples:

```python
# Count from 1 to 5
count = 1

while count <= 5:
    print(count)
    count += 1
# Output: 1, 2, 3, 4, 5

# Sum numbers until total exceeds 50
total = 0
number = 1

while total <= 50:
    total += number
    number += 1

print(f"Total: {total}, Last number: {number - 1}")
# Output: Total: 55, Last number: 10
```

### When to Use for vs while:

| Loop Type | When to Use | Example |
|-----------|-------------|---------|
| `for` | You know how many iterations | "Print numbers 1 to 10" |
| `while` | You don't know iterations in advance | "Keep asking until user enters 'quit'" |

## Loop Control Statements

Python provides keywords to control loop execution:

### 1. break - Exit the Loop

The `break` statement immediately exits the loop.

```python
# Find first number divisible by 7
for i in range(1, 100):
    if i % 7 == 0:
        print(f"First number divisible by 7: {i}")
        break
# Output: First number divisible by 7: 7

# Search for an item
fruits = ["apple", "banana", "orange", "mango"]
search = "orange"

for fruit in fruits:
    if fruit == search:
        print(f"Found {search}!")
        break
# Output: Found orange!
```

### 2. continue - Skip to Next Iteration

The `continue` statement skips the rest of the current iteration and moves to the next one.

```python
# Print only odd numbers from 1 to 10
for i in range(1, 11):
    if i % 2 == 0:
        continue  # Skip even numbers
    print(i)
# Output: 1, 3, 5, 7, 9

# Skip negative numbers
numbers = [5, -3, 8, -1, 12, -7, 4]

for num in numbers:
    if num < 0:
        continue  # Skip negative numbers
    print(num)
# Output: 5, 8, 12, 4
```

### 3. pass - Do Nothing

The `pass` statement is a placeholder that does nothing. Useful when syntax requires code but you don't want to execute anything.

```python
# Placeholder for future code
for i in range(5):
    if i == 3:
        pass  # TODO: Add special handling later
    else:
        print(i)
# Output: 0, 1, 2, 4 (skips 3 without error)
```

## Nested Loops

You can place loops inside other loops. This is useful for working with 2D data or creating patterns.

### Examples:

```python
# Multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} x {j} = {i * j}")
    print()  # Empty line after each number

# Output:
# 1 x 1 = 1
# 1 x 2 = 2
# 1 x 3 = 3
#
# 2 x 1 = 2
# 2 x 2 = 4
# 2 x 3 = 6
# ...

# Pattern printing
for i in range(1, 5):
    for j in range(i):
        print("*", end="")
    print()  # New line after each row

# Output:
# *
# **
# ***
# ****
```

## Common Loop Patterns

### Pattern 1: Accumulator Pattern

```python
# Sum of numbers
numbers = [1, 2, 3, 4, 5]
total = 0

for num in numbers:
    total += num

print(total)  # Output: 15
```

### Pattern 2: Counter Pattern

```python
# Count positive numbers
numbers = [5, -3, 8, -1, 12, 7]
positive_count = 0

for num in numbers:
    if num > 0:
        positive_count += 1

print(positive_count)  # Output: 4
```

### Pattern 3: Search Pattern

```python
# Find if item exists
items = ["apple", "banana", "orange"]
found = False

for item in items:
    if item == "banana":
        found = True
        break

print(found)  # Output: True
```

### Pattern 4: List Building Pattern

```python
# Create list of squares
squares = []

for i in range(1, 6):
    squares.append(i ** 2)

print(squares)  # Output: [1, 4, 9, 16, 25]
```

## Loop with else Clause

Python allows an `else` clause with loops. The `else` block executes when the loop completes normally (without `break`).

```python
# Search with else
numbers = [2, 4, 6, 8]

for num in numbers:
    if num % 2 != 0:
        print("Found odd number")
        break
else:
    print("All numbers are even")
# Output: All numbers are even

# Example with break
numbers = [2, 4, 7, 8]

for num in numbers:
    if num % 2 != 0:
        print(f"Found odd number: {num}")
        break
else:
    print("All numbers are even")
# Output: Found odd number: 7
```

## Practice Exercises

Before taking the quiz, try these exercises:

1. Write a loop to print the first 10 multiples of 5
2. Create a program that sums all even numbers from 1 to 50
3. Write a program to find the factorial of a number (e.g., 5! = 5 × 4 × 3 × 2 × 1)
4. Use nested loops to create a 5x5 grid of numbers
5. Write a program that counts how many times the letter 'a' appears in a string

## Common Mistakes to Avoid

1. **Infinite while loops**: Always ensure the condition will eventually become False
2. **Off-by-one errors**: Remember `range(5)` gives 0-4, not 1-5
3. **Modifying list while iterating**: Can cause unexpected behavior
4. **Forgetting to update loop variable**: In while loops, always update the variable used in the condition

## Key Takeaways

- **for loops** iterate over sequences (lists, strings, ranges)
- **while loops** repeat while a condition is True
- **range()** generates number sequences for iteration
- **break** exits the loop immediately
- **continue** skips to the next iteration
- **Nested loops** allow working with multi-dimensional data
- **Loop + else** executes when loop completes without break

Loops are essential for automating repetitive tasks and processing collections of data. They work hand-in-hand with conditions to create powerful programs!

## What's Next?

Congratulations on completing the Python Basics module! Next, you'll move on to the Python Intermediate module where you'll learn about **functions** - how to organize your code into reusable blocks. Functions often contain loops and conditions!
