# Nested Functions and Nonlocal Variables: A Step-by-Step Breakdown

## The Code Example

```python
def outer_function():
    count = 0
    
    def inner_function():
        nonlocal count
        count += 1
        print(count)
        
    inner_function()  # Output: 1
    inner_function()  # Output: 2
    
outer_function()
```

## Concept Overview

This example demonstrates:
1. Nested functions (defining a function inside another function)
2. Variable scope in Python
3. The `nonlocal` keyword for accessing variables from enclosing scopes

## Step-by-Step Breakdown

### Step 1: Calling the Outer Function
```python
outer_function()
```
This executes the code inside `outer_function()`.

### Step 2: Variable Initialization
```python
count = 0
```
A variable named `count` is initialized with the value `0` in the outer function's scope.

### Step 3: Inner Function Definition
```python
def inner_function():
    nonlocal count
    count += 1
    print(count)
```
- The inner function is defined but not yet executed
- The `nonlocal` keyword declares that `count` refers to the variable from the enclosing function's scope
- Without `nonlocal`, Python would create a new local variable named `count` inside the inner function

### Step 4: First Call to Inner Function
```python
inner_function()  # Output: 1
```
When `inner_function()` is called for the first time:
- It accesses the `count` variable from the outer scope (currently 0)
- Increments it by 1 (now `count` equals 1)
- Prints the current value: `1`

### Step 5: Second Call to Inner Function
```python
inner_function()  # Output: 2
```
When `inner_function()` is called for the second time:
- It accesses the updated `count` variable (currently 1)
- Increments it by 1 (now `count` equals 2)
- Prints the current value: `2`

### Step 6: Outer Function Completes
The `outer_function()` finishes execution. The `count` variable and `inner_function()` are no longer accessible.

## Key Points to Understand

1. **Scope Persistence**: Variables defined in the outer function remain "alive" as long as the outer function is executing.

2. **Nested Functions**: Inner functions can access variables from their containing functions.

3. **The `nonlocal` Keyword**: This tells Python that you want to modify a variable from the enclosing (non-global) scope, not create a new local variable.

4. **Difference from `global`**: While `global` lets you access variables from the module's top level, `nonlocal` accesses variables from the nearest enclosing scope.

## What Would Happen Without `nonlocal`?

If we removed the `nonlocal` declaration:

```python
def outer_function():
    count = 0
    
    def inner_function():
        # nonlocal count  # Removed
        count += 1        # This would cause an error
        print(count)
        
    inner_function()
    inner_function()
    
outer_function()
```

This would raise an `UnboundLocalError` because:
1. Without `nonlocal`, Python assumes `count` is a local variable in `inner_function()`
2. The line `count += 1` tries to reference `count` before it's been assigned in the local scope

## Real-World Applications

This pattern is useful for:
- Creating counters and accumulators
- Maintaining state between function calls
- Implementing closures in Python
- Creating factory functions that remember values

## Example: A Counter Factory

```python
def create_counter(start=0):
    count = start
    
    def increment():
        nonlocal count
        count += 1
        return count
        
    return increment

# Create two separate counters
counter1 = create_counter()
counter2 = create_counter(10)

print(counter1())  # Output: 1
print(counter1())  # Output: 2
print(counter2())  # Output: 11
print(counter1())  # Output: 3
```

This demonstrates how nonlocal variables can create functions that maintain their own persistent state.
