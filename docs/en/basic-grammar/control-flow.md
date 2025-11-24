---
order: 4
---

# Control Flow: Conditionals and Loops

## Introduction

Control flow statements allow you to execute different blocks of code based on conditions or repeat code execution. Python provides `if` statements, `for` loops, and `while` loops to control the flow of your program.

## Conditional Statements (if-elif-else)

Conditional statements allow you to execute different code based on conditions:

```python
age = 18

if age < 13:
    print("You are a child")
elif age < 18:
    print("You are a teenager")
elif age < 65:
    print("You are an adult")
else:
    print("You are a senior")
```

## For Loops

`for` loops are used to iterate over sequences (like lists, strings, or ranges):

```python
# Iterating over a list
fruits = ["apple", "banana", "orange"]
for fruit in fruits:
    print(f"I like {fruit}")

# Using range()
for i in range(5):
    print(f"Number: {i}")

# Iterating over a string
for char in "Python":
    print(char)
```

## While Loops

`while` loops repeat code while a condition is true:

```python
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1

print("Loop finished!")
```

## Break and Continue

- `break`: Exit the loop
- `continue`: Skip the current iteration and continue with the next

```python
# Break example
for i in range(10):
    if i == 5:
        break
    print(i)

# Continue example
for i in range(5):
    if i == 2:
        continue
    print(i)
```

## Exercise: Number Guessing Game

Create a game where the computer picks a random number and the player tries to guess it.

### Sample Solution

```python
import random

def guess_number_game():
    print("=== Number Guessing Game ===")
    print("I'm thinking of a number between 1 and 100.")

    # Generate random number
    secret_number = random.randint(1, 100)
    attempts = 0
    max_attempts = 10

    while attempts < max_attempts:
        try:
            guess = int(input(f"\nAttempt {attempts + 1}/{max_attempts} - Enter your guess: "))
            attempts += 1

            if guess < 1 or guess > 100:
                print("Please enter a number between 1 and 100!")
                continue

            if guess < secret_number:
                print("Too low! Try again.")
            elif guess > secret_number:
                print("Too high! Try again.")
            else:
                print(f"🎉 Congratulations! You guessed it in {attempts} attempts!")
                break

        except ValueError:
            print("Invalid input! Please enter a number.")
            attempts -= 1  # Don't count invalid attempts

    else:
        print(f"\nGame Over! The correct answer was {secret_number}.")

    # Ask to play again
    play_again = input("\nWould you like to play again? (yes/no): ").lower()
    if play_again in ['yes', 'y']:
        guess_number_game()

# Run the game
guess_number_game()
```

## Exercise: Multiplication Table

Create a program that prints a multiplication table.

### Sample Solution

```python
def multiplication_table():
    print("=== Multiplication Table ===\n")

    # Outer loop: rows
    for i in range(1, 10):
        # Inner loop: columns
        for j in range(1, 10):
            result = i * j
            print(f"{i} × {j} = {result:2}", end="  ")
        print()  # New line

# Run the program
multiplication_table()
```

## Nested Loops

Loops can be nested inside other loops:

```python
# Print a pattern
for i in range(5):
    for j in range(i + 1):
        print("*", end="")
    print()
```

Output:

```
*
**
***
****
*****
```

## Key Concepts

1. **Conditional Statements**: Use `if`, `elif`, and `else` to execute code based on conditions
2. **For Loops**: Iterate over sequences or perform a fixed number of operations
3. **While Loops**: Repeat code while a condition is true
4. **Break**: Exit a loop immediately
5. **Continue**: Skip the current iteration and continue with the next
6. **Nested Loops**: Use loops inside loops

## Practice Challenges

1. Create a program that prints all prime numbers between 1 and 100
2. Write a program that calculates the factorial of a number
3. Create a FizzBuzz program (1-100, print Fizz for multiples of 3, Buzz for 5, FizzBuzz for 15)
4. Build a simple menu-driven program with multiple options
5. Create a program that reverses a string or number
