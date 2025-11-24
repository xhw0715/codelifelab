---
order: 3
---

# Variables and Data Types

## Introduction

Variables are containers for storing data values. Python has various data types including numbers, strings, booleans, and more. Understanding these fundamental concepts is essential for any Python programmer.

## Basic Data Types

### Numbers

Python supports integers, floating-point numbers, and complex numbers:

```python
# Integer
age = 25
print(f"Age: {age}, Type: {type(age)}")

# Float
price = 19.99
print(f"Price: {price}, Type: {type(price)}")

# Complex
complex_num = 3 + 4j
print(f"Complex: {complex_num}, Type: {type(complex_num)}")
```

### Strings

Strings are sequences of characters enclosed in quotes:

```python
# Single quotes
name = 'Alice'

# Double quotes
message = "Hello, World!"

# Triple quotes for multi-line strings
description = """This is a
multi-line string
in Python."""

print(name)
print(message)
print(description)
```

### Booleans

Boolean values represent True or False:

```python
is_student = True
has_graduated = False

print(f"Is student: {is_student}")
print(f"Has graduated: {has_graduated}")
```

## Type Conversion

You can convert between different data types:

```python
# String to integer
age_str = "25"
age_int = int(age_str)
print(f"Converted: {age_int}, Type: {type(age_int)}")

# Integer to string
number = 42
number_str = str(number)
print(f"Converted: {number_str}, Type: {type(number_str)}")

# String to float
price_str = "19.99"
price_float = float(price_str)
print(f"Converted: {price_float}, Type: {type(price_float)}")
```

## Exercise: Temperature Converter

Create a program that converts temperatures between Celsius and Fahrenheit.

### Sample Solution

```python
def temperature_converter():
    print("=== Temperature Converter ===")
    print("1. Celsius to Fahrenheit")
    print("2. Fahrenheit to Celsius")

    choice = input("\nEnter your choice (1/2): ")

    if choice == '1':
        celsius = float(input("Enter temperature in Celsius: "))
        fahrenheit = (celsius * 9/5) + 32
        print(f"{celsius}°C = {fahrenheit:.2f}°F")

    elif choice == '2':
        fahrenheit = float(input("Enter temperature in Fahrenheit: "))
        celsius = (fahrenheit - 32) * 5/9
        print(f"{fahrenheit}°F = {celsius:.2f}°C")

    else:
        print("Invalid choice!")

# Run the converter
temperature_converter()
```

## Key Concepts

1. **Variable Assignment**: Use `=` to assign values to variables
2. **Dynamic Typing**: Python automatically determines the data type
3. **Type Checking**: Use `type()` to check a variable's type
4. **Type Conversion**: Convert between types using `int()`, `float()`, `str()`, etc.
5. **String Formatting**: Use f-strings for easy string interpolation

## Practice Challenges

1. Create a BMI (Body Mass Index) calculator that takes weight and height as input
2. Build a simple calculator that performs basic arithmetic operations
3. Create a program that swaps the values of two variables
4. Write a program that checks if a number is even or odd
5. Build a currency converter that converts between different currencies
