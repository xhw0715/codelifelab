---
order: 5
---

# Functions

## Introduction

Functions are reusable blocks of code that perform specific tasks. They help organize code, make it more readable, and reduce repetition. In Python, you define functions using the `def` keyword.

## Basic Function Syntax

```python
def greet():
    print("Hello, World!")

# Call the function
greet()
```

## Functions with Parameters

Functions can accept input values called parameters:

```python
def greet_person(name):
    print(f"Hello, {name}!")

greet_person("Alice")
greet_person("Bob")
```

## Multiple Parameters

Functions can have multiple parameters:

```python
def add_numbers(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")

add_numbers(5, 3)
add_numbers(10, 20)
```

## Return Values

Functions can return values using the `return` keyword:

```python
def multiply(a, b):
    return a * b

result = multiply(4, 5)
print(f"Result: {result}")

# Use directly in expressions
total = multiply(3, 7) + multiply(2, 4)
print(f"Total: {total}")
```

## Default Parameters

You can provide default values for parameters:

```python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")

greet("Alice")              # Uses default greeting
greet("Bob", "Hi")          # Uses custom greeting
greet("Charlie", "Good morning")
```

## Exercise: Calculator Functions

Create a calculator with separate functions for each operation.

### Sample Solution

```python
def add(a, b):
    """Add two numbers"""
    return a + b

def subtract(a, b):
    """Subtract b from a"""
    return a - b

def multiply(a, b):
    """Multiply two numbers"""
    return a * b

def divide(a, b):
    """Divide a by b"""
    if b == 0:
        return "Error: Cannot divide by zero"
    return a / b

def calculator():
    print("=== Simple Calculator ===")
    print("Operations:")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Exit")

    while True:
        choice = input("\nEnter operation (1-5): ")

        if choice == '5':
            print("Thank you for using the calculator!")
            break

        if choice not in ['1', '2', '3', '4']:
            print("Invalid choice!")
            continue

        try:
            num1 = float(input("Enter first number: "))
            num2 = float(input("Enter second number: "))

            if choice == '1':
                result = add(num1, num2)
                print(f"Result: {num1} + {num2} = {result}")
            elif choice == '2':
                result = subtract(num1, num2)
                print(f"Result: {num1} - {num2} = {result}")
            elif choice == '3':
                result = multiply(num1, num2)
                print(f"Result: {num1} × {num2} = {result}")
            elif choice == '4':
                result = divide(num1, num2)
                print(f"Result: {num1} ÷ {num2} = {result}")

        except ValueError:
            print("Invalid input! Please enter numbers.")

# Run the calculator
calculator()
```

## Exercise: Text Analyzer

Create functions to analyze text strings.

### Sample Solution

```python
def count_words(text):
    """Count the number of words in text"""
    words = text.split()
    return len(words)

def count_vowels(text):
    """Count the number of vowels in text"""
    vowels = "aeiouAEIOU"
    count = 0
    for char in text:
        if char in vowels:
            count += 1
    return count

def reverse_text(text):
    """Reverse the text"""
    return text[::-1]

def is_palindrome(text):
    """Check if text is a palindrome"""
    # Remove spaces and convert to lowercase
    cleaned = text.replace(" ", "").lower()
    return cleaned == cleaned[::-1]

def text_analyzer():
    print("=== Text Analyzer ===")

    text = input("Enter text to analyze: ")

    print(f"\nAnalysis Results:")
    print(f"Word count: {count_words(text)}")
    print(f"Vowel count: {count_vowels(text)}")
    print(f"Reversed: {reverse_text(text)}")
    print(f"Is palindrome: {is_palindrome(text)}")

# Run the analyzer
text_analyzer()
```

## Variable Scope

Variables defined inside a function are local to that function:

```python
def my_function():
    local_var = "I'm local"
    print(local_var)

my_function()
# print(local_var)  # This would cause an error

# Global variables
global_var = "I'm global"

def another_function():
    print(global_var)  # Can access global variables

another_function()
```

## Docstrings

Use docstrings to document your functions:

```python
def calculate_area(length, width):
    """
    Calculate the area of a rectangle.

    Parameters:
    length (float): The length of the rectangle
    width (float): The width of the rectangle

    Returns:
    float: The area of the rectangle
    """
    return length * width

# Access docstring
print(calculate_area.__doc__)
```

## Key Concepts

1. **Function Definition**: Use `def` to define functions
2. **Parameters**: Input values passed to functions
3. **Return Values**: Use `return` to send values back from functions
4. **Default Parameters**: Provide default values for optional parameters
5. **Scope**: Variables inside functions are local by default
6. **Docstrings**: Document functions with triple-quoted strings

## Practice Challenges

1. Create a function that checks if a number is prime
2. Write a function that generates the Fibonacci sequence up to n terms
3. Create a function that converts between different units (meters to feet, kg to pounds, etc.)
4. Build a function that validates email addresses
5. Write a function that finds the largest/smallest number in a list
