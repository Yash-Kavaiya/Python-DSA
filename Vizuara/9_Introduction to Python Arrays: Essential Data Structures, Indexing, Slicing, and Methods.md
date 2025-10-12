# 🐍 Python Arrays and Lists - Complete Guide

> **Course**: Data Structures and Algorithms in Python  
> **Topic**: Arrays, Lists, and List Methods  
> **Duration**: 44 minutes

***

## 📚 Introduction to Arrays

**Arrays** are data structures used to store multiple items in a single variable. Unlike languages such as Java or C++, Python arrays are **dynamic** in nature—their size is not fixed and can grow or shrink as needed.[1][2]

### Key Differences: Arrays vs Lists

Python offers two primary structures for storing multiple values:[2][3][1]

| Feature | Array Module | Python Lists |
|---------|-------------|--------------|
| **Type Restriction** | Can only store similar data types (e.g., integers only) | Can store mixed data types (integers, strings, floats, booleans, objects) |
| **Flexibility** | Less flexible | Highly flexible |
| **Common Usage** | Specialized numerical operations | General-purpose programming |
| **Dynamic Size** | Yes | Yes |

Throughout this course, **Python Lists** will be the primary focus due to their flexibility and widespread usage.[1][2]

***

## 🔢 Array Basics

### Creating an Array

```python
arr = [10, 20, 30, 40, 50, 60, 70, 80, 90]
print(arr)  # Output: [10, 20, 30, 40, 50, 60, 70, 80, 90]
```

### Array Length

The **length** of an array refers to the number of elements it contains:[2][1]

```python
print(len(arr))  # Output: 9
```

### Elements and Indexing

**Elements** are the values stored in an array. Each element is identified by a unique **index**.[3][1][2]

#### Positive Indexing

Positive indexing starts from `0` for the first element and increases by `1` for each subsequent element:[1][2]

```
Index:    0   1   2   3   4   5   6   7   8
Element: 10  20  30  40  50  60  70  80  90
```

The last index is always `len(array) - 1`.[1]

#### Negative Indexing

Negative indexing starts from `-1` for the last element and decreases by `1` moving backward:[2][1]

```
Index:   -9  -8  -7  -6  -5  -4  -3  -2  -1
Element: 10  20  30  40  50  60  70  80  90
```

***

## 🎯 Accessing Array Elements

```python
arr = [10, 20, 30, 40, 50, 60, 70, 80, 90]

# Using positive indexing
print(arr[3])   # Output: 40
print(arr[5])   # Output: 60
print(arr[0])   # Output: 10

# Using length-based indexing
print(arr[len(arr) - 1])  # Output: 90 (last element)

# Using negative indexing
print(arr[-1])   # Output: 90
print(arr[-5])   # Output: 50
```

***

## 🔁 Iterating Over Arrays

### Method 1: Index-Based Iteration

```python
for i in range(len(arr)):
    print(arr[i])
```

**Time Complexity**: $$ O(n) $$  
**Space Complexity**: $$ O(1) $$[2][1]

### Method 2: Element-Based Iteration

```python
for element in arr:
    print(element)
```

**Time Complexity**: $$ O(n) $$  
**Space Complexity**: $$ O(1) $$[1][2]

### Method 3: List Comprehension

```python
[print(i) for i in arr]
```

**Time Complexity**: $$ O(n) $$  
**Space Complexity**: $$ O(n) $$** (creates a new array)[2][1]

```mermaid
flowchart TD
    A[Start Iteration] --> B{Index-Based?}
    B -->|Yes| C[Use range/len]
    B -->|No| D{Element-Based?}
    C --> E[Access arr[i]]
    D -->|Yes| F[Direct element access]
    D -->|No| G[List Comprehension]
    E --> H[Process Element]
    F --> H
    G --> I[Create New Array]
    H --> J[Print/Store]
    I --> J
    J --> K{More Elements?}
    K -->|Yes| B
    K -->|No| L[End]
```

***

## ✂️ Array Slicing

Slicing creates a **subset** of an array using the syntax `arr[start:end:step]`:[1][2]

| Parameter | Description | Default |
|-----------|-------------|---------|
| `start` | Initial position (inclusive) | `0` |
| `end` | End position (exclusive) | `len(arr)` |
| `step` | Jump/stride between elements | `1` |

### Slicing Examples

```python
arr = [10, 20, 30, 40, 50, 60, 70, 80, 90]

# Basic slicing
sliced_arr = arr[0:3:1]  # Output: [10, 20, 30]

# Using defaults
sliced_arr = arr[:len(arr)]  # Output: [10, 20, 30, 40, 50, 60, 70, 80, 90]

# Negative indexing
sliced_arr = arr[-4:-2]  # Output: [60, 70]

# Single element
sliced_arr = arr[-4:-3]  # Output: [60]
```

***

## 🛠️ List Methods

[2]

### 1. `append()` - Add Element at End

Adds an element to the **end** of the list:[3][2]

```python
arr.append(120)
print(arr)  # Output: [..., 90, 120]
```

**Time Complexity**: $$ O(1) $$  
**Space Complexity**: $$ O(1) $$[1][2]

***

### 2. `insert()` - Add Element at Specified Position

Inserts an element at a **specific index** and shifts subsequent elements to the right:[3][2]

```python
arr.insert(1, 150)
print(arr)  # Output: [10, 150, 20, 30, ...]
```

#### Custom Insert Implementation

```python
def our_custom_insert(position, val, array):
    # Step 1: Append None to create space
    array.append(None)
    
    # Step 2: Shift elements to the right
    for i in range(len(array) - 1, position, -1):
        array[i] = array[i - 1]
    
    # Step 3: Insert the value
    array[position] = val

arr = [10, 20, 30, 40, 50, 60, 70, 80, 90]
our_custom_insert(2, 200, arr)
print(arr)  # Output: [10, 20, 200, 30, ...]
```

**Time Complexity**: $$ O(n) $$ (worst case: inserting at index 0)  
**Space Complexity**: $$ O(1) $$[2][1]

```mermaid
sequenceDiagram
    participant User
    participant Array
    participant InsertFunc
    
    User->>InsertFunc: insert(index=1, value=150)
    InsertFunc->>Array: append(None)
    Note over Array: [10, 20, 30, ..., 90, None]
    
    InsertFunc->>Array: Shift 90 → last position
    InsertFunc->>Array: Shift 80 → position 8
    InsertFunc->>Array: Continue shifting...
    InsertFunc->>Array: Shift 20 → position 2
    
    InsertFunc->>Array: arr[1] = 150
    Note over Array: [10, 150, 20, 30, ..., 90]
    
    Array-->>User: Return modified array
```

***

### 3. `extend()` - Add Two Lists

Combines two lists by appending elements from the second list to the first:[3][2]

```python
arr2 = [45, 55, 85]
arr.extend(arr2)
print(arr)  # Output: [..., 90, 45, 55, 85]
```

**Time Complexity**: $$ O(n) $$ (where $$ n $$ is the size of `arr2`)  
**Space Complexity**: $$ O(n) $$[1][2]

***

### 4. `pop()` - Remove Element

Removes and returns the **last element** by default, or an element at a **specified index**:[3][2]

```python
# Remove last element
arr.pop()
print(arr)  # Removes 90

# Remove element at index 1
arr.pop(1)
print(arr)  # Removes element at index 1 (20)
```

**Time Complexity**: 
- $$ O(1) $$ for last element  
- $$ O(n) $$ for arbitrary index (requires shifting)[2][1]

**Space Complexity**: $$ O(1) $$[1][2]

***

### 5. `remove()` - Remove First Occurrence of Value

Searches for the **first occurrence** of a value and removes it:[3][2]

```python
arr.remove(50)
print(arr)  # Removes 50 and shifts remaining elements left
```

**Time Complexity**: $$ O(n) $$ (linear search + shifting)  
**Space Complexity**: $$ O(1) $$[2][1]

```mermaid
flowchart LR
    A[Start: remove 50] --> B{arr[0] == 50?}
    B -->|No| C{arr[1] == 50?}
    C -->|No| D{arr[2] == 50?}
    D -->|No| E{arr[3] == 50?}
    E -->|No| F{arr[4] == 50?}
    F -->|Yes| G[Found at index 4]
    G --> H[Remove element]
    H --> I[Left-shift elements]
    I --> J[End]
    
    style F fill:#90EE90
    style G fill:#FFD700
    style I fill:#FF6347
```

***

## 📊 Complexity Summary Table

| Operation | Time Complexity | Space Complexity | Notes |
|-----------|----------------|------------------|-------|
| **Access Element** | $$ O(1) $$ | $$ O(1) $$ | Direct indexing |
| **Iterate (Index)** | $$ O(n) $$ | $$ O(1) $$ | Using `range()` |
| **Iterate (Element)** | $$ O(n) $$ | $$ O(1) $$ | Using `for element in arr` |
| **List Comprehension** | $$ O(n) $$ | $$ O(n) $$ | Creates new array |
| **Slice** | $$ O(k) $$ | $$ O(k) $$ | Where $$ k $$ is slice size |
| **append()** | $$ O(1) $$ | $$ O(1) $$ | Add to end |
| **insert()** | $$ O(n) $$ | $$ O(1) $$ | Worst case: insert at start |
| **extend()** | $$ O(n) $$ | $$ O(n) $$ | Where $$ n $$ is extension size |
| **pop()** (last) | $$ O(1) $$ | $$ O(1) $$ | Remove last element |
| **pop(index)** | $$ O(n) $$ | $$ O(1) $$ | Requires shifting |
| **remove()** | $$ O(n) $$ | $$ O(1) $$ | Search + shift |

***

## 🎓 Key Takeaways

⚡ **Dynamic Nature**: Python lists automatically resize, unlike static arrays in C++/Java[1][2]

⚡ **Indexing**: Supports both positive (0-based) and negative (-1 from end) indexing[3][2][1]

⚡ **Efficiency**: Direct access and append operations are $$ O(1) $$, while insertion/removal from arbitrary positions is $$ O(n) $$[2][1]

⚡ **Methods**: Built-in methods like `append()`, `insert()`, `extend()`, `pop()`, and `remove()` simplify list manipulation[3][2]

⚡ **Slicing**: Powerful syntax for creating sub-arrays without manual loops[1][2]

***

## 💡 Practice Challenge

**Try implementing these operations yourself:**

1. Create a custom `pop()` function that removes an element at a specific index
2. Write a function to reverse an array in-place without using slicing
3. Implement a function that removes all occurrences of a value (not just the first)

<details>
<summary>🔍 Hint for Challenge #1</summary>

Similar to the custom `insert()` function, but you'll need to left-shift elements after the target index, then remove the last element.

</details>

***

**Next Lecture**: Advanced Array Operations and Two-Pointer Techniques 🚀

[1](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/ad1f16da-14c5-46c9-9743-0697d0332ca0/image.jpg?AWSAccessKeyId=ASIA2F3EMEYE6QEUHFQR&Signature=5VrQkcMja5Umd2Wc9vA7l%2B31o38%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIn%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJIMEYCIQCruMBdlym3r%2Fu6nGDIQ7ltaHoF4riMAkchXyTy1HeyxwIhAN8qL7j1fGSPPOzjTk63%2FxPhqGT3Tb5CzFi3FfVBTiowKvEECDIQARoMNjk5NzUzMzA5NzA1IgxBAtz39E6w%2BZUG4WEqzgTwzpT0fhh0FzYCgmiCx5%2BVvIshyJaSlFVJryTXd%2Fv8lSlqJ%2BTb4%2Bs%2B4ZgblMIZojascE9azRXg0Qh3GpUDbgBuTVJQgaETlUT3SlxF21COOohyqdQMNRzxmG0Eicj2MCmWFdEo0GZ2oOEP7gJ%2Br4kyspfhrUn6KqIGIkL5lYfHh7shUPUpj%2BJs12x3P4dPU4SispWQQhHDqcHZzH3LzVqLyZYepyKhcp3O%2B4c5Ygk9IMDhcHfyUv4U9cL19UKhh%2FPFx9WDFwo61SKrVwXH4eJ%2F2bVcF0rBYurCuDMXN6oZmPmcu7ZXt5Fa%2BdiISNPe1NodRudXhxDCVQUsHFy1HpZFxhoqfDUrdxGdvcOt1jtpwK3C0%2FLZYnxmG%2FPPObldwqpBLNEcK4iQWi%2Ft5rZXySb%2Byqi694T85VVJfNKybSE5mjLRRXr2JUtNTQ0KFKHqAbM686r7hiom9tsb%2F2OpedH%2F4zCKbbi5w6%2B5CTgAkX88z8EdDr0CGwgm8AwUzZCsVDDOsKYFgWWw8wc0s8htabzNHoGqom0xab77Dj2aAQTu8JSVJkhL7Lq%2BRzYWi4iIiubh1oe8xglG0hyQLikVRy4aiJ9KEv7voPRkeb%2B4J9fJT0AYY9CV5%2FiIia1GMjuWjSZyqpiElnuYdd296R6OkRdocU9u3fsXEouAAQblJCvQrLXAE7WZgj4nG9OkIngT38ZCnnsKx6xoPPYCwC9ukq9lAzlD4T0nI07VeMnQF%2B89PwLTeIdigB775C%2BKur04SamU9thEKhXP9M%2Fc7uj4fTCeuq%2FHBjqZATmCfjtDumOP2AjEJNPXLbAhf5Y7Bl8wsjro7Pm1L%2BmMl%2FllRFAnIwp%2BqkNrM4J7vTQy29Qdjc%2F16S1RmEWSrNYH2XMUixwc0XJNVuxcSYzHCT9PDHT%2BCSlUcmZ4qidWBoDwRCNs7QVuLr8W4U0yWkKOYBeImOVBM33%2BUWdhTCghByUFbN0ba5LHwgbBkwil5Uj7SwWH%2FBisPg%3D%3D&Expires=1760288852)
[2](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/e3dc8b7e-af0a-4b3d-9116-e7b611db2eca/image.jpg?AWSAccessKeyId=ASIA2F3EMEYE6QEUHFQR&Signature=dOM9HQZGr8bPqAZCefCJ%2Fa%2Fqvus%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIn%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJIMEYCIQCruMBdlym3r%2Fu6nGDIQ7ltaHoF4riMAkchXyTy1HeyxwIhAN8qL7j1fGSPPOzjTk63%2FxPhqGT3Tb5CzFi3FfVBTiowKvEECDIQARoMNjk5NzUzMzA5NzA1IgxBAtz39E6w%2BZUG4WEqzgTwzpT0fhh0FzYCgmiCx5%2BVvIshyJaSlFVJryTXd%2Fv8lSlqJ%2BTb4%2Bs%2B4ZgblMIZojascE9azRXg0Qh3GpUDbgBuTVJQgaETlUT3SlxF21COOohyqdQMNRzxmG0Eicj2MCmWFdEo0GZ2oOEP7gJ%2Br4kyspfhrUn6KqIGIkL5lYfHh7shUPUpj%2BJs12x3P4dPU4SispWQQhHDqcHZzH3LzVqLyZYepyKhcp3O%2B4c5Ygk9IMDhcHfyUv4U9cL19UKhh%2FPFx9WDFwo61SKrVwXH4eJ%2F2bVcF0rBYurCuDMXN6oZmPmcu7ZXt5Fa%2BdiISNPe1NodRudXhxDCVQUsHFy1HpZFxhoqfDUrdxGdvcOt1jtpwK3C0%2FLZYnxmG%2FPPObldwqpBLNEcK4iQWi%2Ft5rZXySb%2Byqi694T85VVJfNKybSE5mjLRRXr2JUtNTQ0KFKHqAbM686r7hiom9tsb%2F2OpedH%2F4zCKbbi5w6%2B5CTgAkX88z8EdDr0CGwgm8AwUzZCsVDDOsKYFgWWw8wc0s8htabzNHoGqom0xab77Dj2aAQTu8JSVJkhL7Lq%2BRzYWi4iIiubh1oe8xglG0hyQLikVRy4aiJ9KEv7voPRkeb%2B4J9fJT0AYY9CV5%2FiIia1GMjuWjSZyqpiElnuYdd296R6OkRdocU9u3fsXEouAAQblJCvQrLXAE7WZgj4nG9OkIngT38ZCnnsKx6xoPPYCwC9ukq9lAzlD4T0nI07VeMnQF%2B89PwLTeIdigB775C%2BKur04SamU9thEKhXP9M%2Fc7uj4fTCeuq%2FHBjqZATmCfjtDumOP2AjEJNPXLbAhf5Y7Bl8wsjro7Pm1L%2BmMl%2FllRFAnIwp%2BqkNrM4J7vTQy29Qdjc%2F16S1RmEWSrNYH2XMUixwc0XJNVuxcSYzHCT9PDHT%2BCSlUcmZ4qidWBoDwRCNs7QVuLr8W4U0yWkKOYBeImOVBM33%2BUWdhTCghByUFbN0ba5LHwgbBkwil5Uj7SwWH%2FBisPg%3D%3D&Expires=1760288852)
[3](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/1ff92e56-b986-4e14-a974-702884ca302d/image.jpg?AWSAccessKeyId=ASIA2F3EMEYE6QEUHFQR&Signature=ByIlCsqrX7hPoLUocWM5mdYzdt0%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIn%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJIMEYCIQCruMBdlym3r%2Fu6nGDIQ7ltaHoF4riMAkchXyTy1HeyxwIhAN8qL7j1fGSPPOzjTk63%2FxPhqGT3Tb5CzFi3FfVBTiowKvEECDIQARoMNjk5NzUzMzA5NzA1IgxBAtz39E6w%2BZUG4WEqzgTwzpT0fhh0FzYCgmiCx5%2BVvIshyJaSlFVJryTXd%2Fv8lSlqJ%2BTb4%2Bs%2B4ZgblMIZojascE9azRXg0Qh3GpUDbgBuTVJQgaETlUT3SlxF21COOohyqdQMNRzxmG0Eicj2MCmWFdEo0GZ2oOEP7gJ%2Br4kyspfhrUn6KqIGIkL5lYfHh7shUPUpj%2BJs12x3P4dPU4SispWQQhHDqcHZzH3LzVqLyZYepyKhcp3O%2B4c5Ygk9IMDhcHfyUv4U9cL19UKhh%2FPFx9WDFwo61SKrVwXH4eJ%2F2bVcF0rBYurCuDMXN6oZmPmcu7ZXt5Fa%2BdiISNPe1NodRudXhxDCVQUsHFy1HpZFxhoqfDUrdxGdvcOt1jtpwK3C0%2FLZYnxmG%2FPPObldwqpBLNEcK4iQWi%2Ft5rZXySb%2Byqi694T85VVJfNKybSE5mjLRRXr2JUtNTQ0KFKHqAbM686r7hiom9tsb%2F2OpedH%2F4zCKbbi5w6%2B5CTgAkX88z8EdDr0CGwgm8AwUzZCsVDDOsKYFgWWw8wc0s8htabzNHoGqom0xab77Dj2aAQTu8JSVJkhL7Lq%2BRzYWi4iIiubh1oe8xglG0hyQLikVRy4aiJ9KEv7voPRkeb%2B4J9fJT0AYY9CV5%2FiIia1GMjuWjSZyqpiElnuYdd296R6OkRdocU9u3fsXEouAAQblJCvQrLXAE7WZgj4nG9OkIngT38ZCnnsKx6xoPPYCwC9ukq9lAzlD4T0nI07VeMnQF%2B89PwLTeIdigB775C%2BKur04SamU9thEKhXP9M%2Fc7uj4fTCeuq%2FHBjqZATmCfjtDumOP2AjEJNPXLbAhf5Y7Bl8wsjro7Pm1L%2BmMl%2FllRFAnIwp%2BqkNrM4J7vTQy29Qdjc%2F16S1RmEWSrNYH2XMUixwc0XJNVuxcSYzHCT9PDHT%2BCSlUcmZ4qidWBoDwRCNs7QVuLr8W4U0yWkKOYBeImOVBM33%2BUWdhTCghByUFbN0ba5LHwgbBkwil5Uj7SwWH%2FBisPg%3D%3D&Expires=1760288852)
