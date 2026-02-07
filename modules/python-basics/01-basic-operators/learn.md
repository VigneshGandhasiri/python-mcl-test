# Basic Operators in Python

Welcome to your first Python topic! In this lesson, you'll learn about the fundamental operators that allow you to perform calculations and manipulate data in Python.

## What are Operators?

Operators are special symbols in Python that perform operations on values and variables. They are the building blocks for creating expressions and solving problems.

## Types of Basic Operators

### 1. Arithmetic Operators

Arithmetic operators are used to perform mathematical calculations.

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| `+` | Addition | `5 + 3` | `8` |
| `-` | Subtraction | `5 - 3` | `2` |
| `*` | Multiplication | `5 * 3` | `15` |
| `/` | Division | `10 / 3` | `3.333...` |
| `//` | Floor Division | `10 // 3` | `3` |
| `%` | Modulus (Remainder) | `10 % 3` | `1` |
| `**` | Exponentiation | `2 ** 3` | `8` |

#### Examples:

```python
# Basic arithmetic
a = 10
b = 3

print(a + b)   # Output: 13
print(a - b)   # Output: 7
print(a * b)   # Output: 30
print(a / b)   # Output: 3.333333...

# Floor division - gives whole number result
print(a // b)  # Output: 3

# Modulus - gives remainder
print(a % b)   # Output: 1

# Exponentiation - power operation
print(2 ** 3)  # Output: 8 (2 to the power of 3)
```

### 2. Comparison Operators

Comparison operators compare two values and return `True` or `False`.

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |
| `>` | Greater than | `5 > 3` | `True` |
| `<` | Less than | `5 < 3` | `False` |
| `>=` | Greater than or equal | `5 >= 5` | `True` |
| `<=` | Less than or equal | `3 <= 5` | `True` |

#### Examples:

```python
x = 10
y = 5

print(x == y)   # Output: False
print(x != y)   # Output: True
print(x > y)    # Output: True
print(x < y)    # Output: False
print(x >= 10)  # Output: True
print(y <= 5)   # Output: True
```

### 3. Logical Operators

Logical operators are used to combine conditional statements.

| Operator | Description | Example |
|----------|-------------|---------|
| `and` | Returns True if both statements are true | `x > 5 and x < 10` |
| `or` | Returns True if at least one statement is true | `x < 5 or x > 10` |
| `not` | Reverses the result | `not(x > 5)` |

#### Examples:

```python
a = 10
b = 5
c = 15

# AND operator - both conditions must be True
print(a > b and a < c)   # Output: True (10 > 5 AND 10 < 15)
print(a > b and a > c)   # Output: False (10 > 5 but 10 is NOT > 15)

# OR operator - at least one condition must be True
print(a > b or a > c)    # Output: True (10 > 5, so True)
print(a < b or a > c)    # Output: False (both conditions are False)

# NOT operator - reverses the boolean value
print(not(a > b))        # Output: False (a > b is True, not makes it False)
print(not(a < b))        # Output: True (a < b is False, not makes it True)
```

### 4. Assignment Operators

Assignment operators are used to assign values to variables. The most basic is `=`, but Python also provides compound assignment operators.

| Operator | Example | Equivalent to |
|----------|---------|---------------|
| `=` | `x = 5` | `x = 5` |
| `+=` | `x += 3` | `x = x + 3` |
| `-=` | `x -= 3` | `x = x - 3` |
| `*=` | `x *= 3` | `x = x * 3` |
| `/=` | `x /= 3` | `x = x / 3` |
| `//=` | `x //= 3` | `x = x // 3` |
| `%=` | `x %= 3` | `x = x % 3` |
| `**=` | `x **= 3` | `x = x ** 3` |

#### Examples:

```python
# Basic assignment
x = 10
print(x)  # Output: 10

# Compound assignment operators
x += 5    # x = x + 5
print(x)  # Output: 15

x -= 3    # x = x - 3
print(x)  # Output: 12

x *= 2    # x = x * 2
print(x)  # Output: 24

x //= 5   # x = x // 5
print(x)  # Output: 4
```

## Operator Precedence

When multiple operators are used in an expression, Python follows a specific order of operations (similar to mathematics):

1. **Parentheses** `()`
2. **Exponentiation** `**`
3. **Multiplication, Division, Floor Division, Modulus** `*`, `/`, `//`, `%`
4. **Addition, Subtraction** `+`, `-`
5. **Comparison operators** `==`, `!=`, `>`, `<`, `>=`, `<=`
6. **Logical NOT** `not`
7. **Logical AND** `and`
8. **Logical OR** `or`

### Examples:

```python
# Without parentheses
result = 2 + 3 * 4
print(result)  # Output: 14 (3*4=12, then 2+12=14)

# With parentheses to change order
result = (2 + 3) * 4
print(result)  # Output: 20 (2+3=5, then 5*4=20)

# Complex expression
result = 10 + 5 * 2 - 3 ** 2
print(result)  # Output: 11 (3**2=9, 5*2=10, 10+10-9=11)
```

## Practice Exercises

Before taking the quiz, try these exercises:

1. Calculate the area of a rectangle with length 15 and width 8
2. Check if a number 42 is greater than 30 AND less than 50
3. Use the modulus operator to check if 17 is an odd number (odd numbers have remainder 1 when divided by 2)
4. Calculate the average of three numbers: 85, 90, and 78

## Key Takeaways

- **Arithmetic operators** perform mathematical calculations
- **Comparison operators** compare values and return True or False
- **Logical operators** combine multiple conditions
- **Assignment operators** store and update variable values
- Python follows **operator precedence** rules, but you can use parentheses to control the order

Understanding these basic operators is essential for writing Python programs. They form the foundation for more complex operations you'll learn in upcoming topics!

## What's Next?

In the next topic, you'll learn about **conditions** - how to make decisions in your code using if, elif, and else statements. These will use the comparison and logical operators you just learned!
