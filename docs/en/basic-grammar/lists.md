---
order: 6
---

# Lists and List Operations

## Introduction

Lists are one of the most versatile data structures in Python. They are ordered, mutable collections that can store items of different types. Lists are defined using square brackets `[]`.

## Creating Lists

```python
# Empty list
empty_list = []

# List with items
fruits = ["apple", "banana", "orange"]
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]

print(fruits)
print(numbers)
print(mixed)
```

## Accessing List Elements

Use indexing to access elements (indexing starts at 0):

```python
fruits = ["apple", "banana", "orange", "grape"]

print(fruits[0])   # First element: apple
print(fruits[1])   # Second element: banana
print(fruits[-1])  # Last element: grape
print(fruits[-2])  # Second to last: orange
```

## List Slicing

Extract portions of a list using slicing:

```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

print(numbers[2:5])    # [2, 3, 4]
print(numbers[:4])     # [0, 1, 2, 3]
print(numbers[6:])     # [6, 7, 8, 9]
print(numbers[::2])    # [0, 2, 4, 6, 8] (every 2nd element)
print(numbers[::-1])   # Reverse the list
```

## Modifying Lists

Lists are mutable, so you can change their contents:

```python
fruits = ["apple", "banana", "orange"]

# Change an element
fruits[1] = "grape"
print(fruits)  # ['apple', 'grape', 'orange']

# Add elements
fruits.append("mango")        # Add to end
fruits.insert(1, "kiwi")      # Insert at position
print(fruits)

# Remove elements
fruits.remove("orange")       # Remove by value
popped = fruits.pop()         # Remove and return last item
del fruits[0]                 # Delete by index
print(fruits)
```

## Common List Methods

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6]

# Sort
numbers.sort()
print(numbers)  # [1, 1, 2, 3, 4, 5, 6, 9]

# Reverse
numbers.reverse()
print(numbers)  # [9, 6, 5, 4, 3, 2, 1, 1]

# Count occurrences
count = numbers.count(1)
print(f"1 appears {count} times")

# Find index
index = numbers.index(5)
print(f"5 is at index {index}")

# Extend (add multiple items)
numbers.extend([7, 8])
print(numbers)
```

## List Comprehensions

Create lists in a concise way:

```python
# Traditional way
squares = []
for i in range(10):
    squares.append(i ** 2)

# List comprehension
squares = [i ** 2 for i in range(10)]
print(squares)

# With condition
even_squares = [i ** 2 for i in range(10) if i % 2 == 0]
print(even_squares)
```

## Exercise: To-Do List Manager

Create a simple to-do list application.

### Sample Solution

```python
def todo_list_manager():
    todos = []

    print("=== To-Do List Manager ===")
    print("Commands: add, view, complete, delete, quit")

    while True:
        command = input("\nEnter command: ").lower()

        if command == 'quit':
            print("Goodbye!")
            break

        elif command == 'add':
            task = input("Enter task: ")
            if task:
                todos.append({"task": task, "completed": False})
                print(f"Added: {task}")
            else:
                print("Task cannot be empty!")

        elif command == 'view':
            if not todos:
                print("No tasks in your list!")
            else:
                print("\nYour To-Do List:")
                for i, todo in enumerate(todos, 1):
                    status = "✓" if todo["completed"] else " "
                    print(f"{i}. [{status}] {todo['task']}")

        elif command == 'complete':
            if not todos:
                print("No tasks to complete!")
                continue

            try:
                index = int(input("Enter task number to complete: ")) - 1
                if 0 <= index < len(todos):
                    todos[index]["completed"] = True
                    print(f"Completed: {todos[index]['task']}")
                else:
                    print("Invalid task number!")
            except ValueError:
                print("Please enter a valid number!")

        elif command == 'delete':
            if not todos:
                print("No tasks to delete!")
                continue

            try:
                index = int(input("Enter task number to delete: ")) - 1
                if 0 <= index < len(todos):
                    deleted = todos.pop(index)
                    print(f"Deleted: {deleted['task']}")
                else:
                    print("Invalid task number!")
            except ValueError:
                print("Please enter a valid number!")

        else:
            print("Invalid command!")

# Run the manager
todo_list_manager()
```

## Exercise: List Statistics

Create a program that calculates statistics for a list of numbers.

### Sample Solution

```python
def list_statistics():
    print("=== List Statistics Calculator ===")

    # Get numbers from user
    numbers = []
    print("Enter numbers (type 'done' when finished):")

    while True:
        user_input = input("Enter number: ")
        if user_input.lower() == 'done':
            break
        try:
            numbers.append(float(user_input))
        except ValueError:
            print("Invalid number! Try again.")

    if not numbers:
        print("No numbers entered!")
        return

    # Calculate statistics
    total = sum(numbers)
    count = len(numbers)
    average = total / count
    minimum = min(numbers)
    maximum = max(numbers)

    # Sort for median
    sorted_numbers = sorted(numbers)
    if count % 2 == 0:
        median = (sorted_numbers[count//2 - 1] + sorted_numbers[count//2]) / 2
    else:
        median = sorted_numbers[count//2]

    # Display results
    print(f"\n=== Statistics ===")
    print(f"Count: {count}")
    print(f"Sum: {total}")
    print(f"Average: {average:.2f}")
    print(f"Minimum: {minimum}")
    print(f"Maximum: {maximum}")
    print(f"Median: {median}")
    print(f"Range: {maximum - minimum}")

# Run the calculator
list_statistics()
```

## Key Concepts

1. **Creating Lists**: Use square brackets `[]`
2. **Indexing**: Access elements by position (starting at 0)
3. **Slicing**: Extract portions of lists
4. **Mutability**: Lists can be modified after creation
5. **Methods**: Built-in functions like `append()`, `remove()`, `sort()`
6. **List Comprehensions**: Concise way to create lists

## Practice Challenges

1. Create a program that removes duplicates from a list
2. Write a function that finds the second largest number in a list
3. Create a program that merges two sorted lists into one sorted list
4. Build a shopping cart system using lists
5. Write a function that rotates a list by n positions
