# Conditional Statements in Python

Now that you understand operators, let's learn how to make decisions in your code! Conditional statements allow your programs to execute different code blocks based on certain conditions.

## What are Conditional Statements?

Conditional statements help your program make decisions. They check if a condition is `True` or `False` and execute different code accordingly - just like making choices in real life!

## The if Statement

The `if` statement is the most basic conditional. It executes code only if a condition is `True`.

### Syntax:

```python
if condition:
    # code to execute if condition is True
    # note: this code is indented
```

### Examples:

```python
age = 18

if age >= 18:
    print("You are an adult")
# Output: You are an adult

temperature = 30

if temperature > 25:
    print("It's a hot day!")
# Output: It's a hot day!
```

**Important:** Python uses **indentation** (spaces at the beginning of a line) to define code blocks. Always indent code inside an `if` statement.

## The if-else Statement

The `if-else` statement provides an alternative action when the condition is `False`.

### Syntax:

```python
if condition:
    # code to execute if condition is True
else:
    # code to execute if condition is False
```

### Examples:

```python
age = 15

if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")
# Output: You are a minor

score = 85

if score >= 60:
    print("You passed!")
else:
    print("You failed.")
# Output: You passed!
```

## The if-elif-else Statement

When you need to check multiple conditions, use `elif` (else if). Python checks conditions in order and executes the first one that's `True`.

### Syntax:

```python
if condition1:
    # code if condition1 is True
elif condition2:
    # code if condition2 is True
elif condition3:
    # code if condition3 is True
else:
    # code if all conditions are False
```

### Examples:

```python
score = 75

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")
# Output: Grade: C

# Example with temperature
temperature = 15

if temperature > 30:
    print("It's very hot!")
elif temperature > 20:
    print("It's warm")
elif temperature > 10:
    print("It's cool")
else:
    print("It's cold")
# Output: It's cool
```

## Comparison of if, if-else, and if-elif-else

| Statement Type | When to Use | Example Scenario |
|----------------|-------------|------------------|
| `if` | Single condition to check | "If it's raining, take an umbrella" |
| `if-else` | Two possible outcomes | "If age >= 18, adult; otherwise, minor" |
| `if-elif-else` | Multiple conditions | "Grade assignment based on score ranges" |

## Nested Conditional Statements

You can place conditional statements inside other conditional statements. This is called nesting.

### Examples:

```python
age = 25
has_license = True

if age >= 18:
    if has_license:
        print("You can drive")
    else:
        print("You need a license to drive")
else:
    print("You are too young to drive")
# Output: You can drive

# Example with numbers
number = 15

if number > 0:
    if number % 2 == 0:
        print("Positive even number")
    else:
        print("Positive odd number")
else:
    print("Non-positive number")
# Output: Positive odd number
```

## Using Logical Operators in Conditions

You can combine multiple conditions using logical operators (`and`, `or`, `not`) that you learned in the previous topic.

### Examples:

```python
age = 25
has_license = True

# Using AND
if age >= 18 and has_license:
    print("You can drive")
# Output: You can drive

# Using OR
day = "Saturday"

if day == "Saturday" or day == "Sunday":
    print("It's the weekend!")
# Output: It's the weekend!

# Using NOT
is_raining = False

if not is_raining:
    print("You don't need an umbrella")
# Output: You don't need an umbrella

# Complex condition
score = 85
attendance = 90

if score >= 80 and attendance >= 75:
    print("Excellent performance!")
# Output: Excellent performance!
```

## Common Patterns and Best Practices

### Pattern 1: Checking Ranges

```python
age = 35

if 18 <= age <= 65:
    print("Working age")
# Output: Working age

# This is equivalent to:
if age >= 18 and age <= 65:
    print("Working age")
```

### Pattern 2: Checking Multiple Values

```python
fruit = "apple"

if fruit in ["apple", "banana", "orange"]:
    print("This is a common fruit")
# Output: This is a common fruit
```

### Pattern 3: Early Return Pattern

```python
def check_eligibility(age):
    if age < 18:
        return "Too young"
    if age > 65:
        return "Too old"
    return "Eligible"

print(check_eligibility(30))  # Output: Eligible
```

## Indentation Rules

Python uses indentation to define code blocks. Here are the key rules:

1. **Use consistent indentation**: Typically 4 spaces (not tabs)
2. **Indent code inside conditions**: All code in an `if`, `elif`, or `else` block must be indented
3. **Align elif and else**: They should be at the same level as the `if`

### Correct Indentation:

```python
if x > 0:
    print("Positive")
    y = x * 2
elif x < 0:
    print("Negative")
    y = x * -1
else:
    print("Zero")
    y = 0
```

### Incorrect Indentation:

```python
# This will cause an IndentationError!
if x > 0:
print("Positive")  # Missing indentation

if x > 0:
    print("Positive")
  elif x < 0:      # Incorrect indentation for elif
    print("Negative")
```

## Practice Exercises

Before taking the quiz, try these exercises:

1. Write a program that checks if a number is positive, negative, or zero
2. Create a program that determines ticket price based on age:
   - Children (under 12): $10
   - Adults (12-64): $20
   - Seniors (65+): $15
3. Write a program that checks if a year is a leap year (divisible by 4, but not by 100 unless also divisible by 400)
4. Create a program that determines if a student gets a scholarship based on:
   - Score >= 90 AND attendance >= 80

## Key Takeaways

- **if statements** execute code when a condition is True
- **if-else** provides an alternative when the condition is False
- **if-elif-else** checks multiple conditions in order
- **Logical operators** (`and`, `or`, `not`) can combine conditions
- **Indentation** is crucial in Python - it defines code blocks
- Conditions can be **nested** for complex decision-making

Conditional statements are essential for creating programs that can make decisions and respond to different situations. They work together with the operators you learned previously!

## What's Next?

In the next topic, you'll learn about **loops** - how to repeat code multiple times automatically. Loops often use conditional statements to determine when to stop repeating!
