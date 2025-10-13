# 🐍 Python Strings: Complete Guide

**String** is a sequence of characters in Python, classified as an **immutable data type**.[1][2]

## 📌 What is a String?

A string in Python is a sequence of characters where each character can be an alphabet, numeric digit, special character, or even a space.[2][1]

```python
str1 = "Hello Coders"
str2 = 'John Doe'
str3 = """Hello Everyone
John here"""
```

### String Creation Methods

| Method | Syntax | Use Case |
|--------|--------|----------|
| Double Quotes | `"text"` | Standard strings |
| Single Quotes | `'text'` | Standard strings |
| Triple Quotes | `"""text"""` | Multi-line strings |

## 🔒 Immutability of Strings

Once a string is created, it **cannot be modified**.[2]

```python
name = "Peter Parker"
name[0] = 'p'  # ❌ TypeError: 'str' object does not support item assignment
```

Strings are read-only, meaning update operations throw errors.[2]

## 📍 String Indexing

Each character in a string has an **index starting from 0**.[1]

```python
name = "Peter Parker"
# Index:  0 1 2 3 4 5 6 7 8 9 10 11

print(name[0])   # Output: P
print(name[6])   # Output: P
```

### Character Data Type

Python does **not have a separate character data type** - single characters are strings with length 1.[2]

```python
print(type(name[0]))  # Output: <class 'str'>
```

## 🔢 ASCII Values

Every character has a unique **ASCII value** (decimal representation) that computers use internally.[1][2]

### ASCII Functions

| Function | Purpose | Example |
|----------|---------|---------|
| `ord()` | Returns ASCII value of character | `ord('a')` → 97 |
| `chr()` | Returns character from ASCII value | `chr(65)` → 'A' |

```python
char = 'a'
print(ord(char))  # Output: 97

ascii_val = 65
print(chr(ascii_val))  # Output: A
```

### 💡 Case Conversion Using ASCII

The ASCII difference between uppercase and lowercase letters is **32**.[1][2]

```python
str_char = 'Z'
ascii_value = ord(str_char)
new_ascii = ascii_value + 32
new_char = chr(new_ascii)
print(new_char)  # Output: z
```

```mermaid
flowchart LR
    A[Capital Letter 'A'] --> B[ASCII: 65]
    C[Small Letter 'a'] --> D[ASCII: 97]
    B --> E[Difference: 32]
    D --> E
```

## 🔄 Looping Through Strings

Use a **for loop** to iterate through each character.[1]

```python
str_val = "Hello World"

for char in str_val:
    print(char)

# Output:
# H
# e
# l
# l
# o
#  
# W
# o
# r
# l
# d
```

## 🔍 Substring Search

The `in` keyword checks if a substring exists within a string, returning a **boolean value**.[2]

```python
str_val = "Hello World"

print("Hello" in str_val)  # Output: True
print("xyz" in str_val)    # Output: False
print("Wor" in str_val)    # Output: True
```

## 🚪 Escape Characters

Escape characters allow special characters inside strings using the **backslash `\`**.[1][2]

### Common Escape Sequences

| Sequence | Purpose | Example |
|----------|---------|---------|
| `\"` | Double quote inside string | `"He said \"Hi\""` |
| `\'` | Single quote inside string | `'It\'s working'` |
| `\n` | New line | `"Hello\nWorld"` |

```python
str_val = "Hello \"World\""
print(str_val)  # Output: Hello "World"

str_val = "Hello\nWorld"
print(str_val)
# Output:
# Hello
# World
```

## ✂️ String Slicing

Extract substrings using **slice notation** `[start:end]` where end is **exclusive**.[2][1]

```python
name = "John Doe"

print(name[1:4])   # Output: ohn
print(name[:4])    # Output: John
print(name[5:])    # Output: Doe
print(name[-4:-2]) # Output: Do
```

```mermaid
graph TD
    A[String: 'John Doe'] --> B[Index 0-3: 'John']
    A --> C[Index 5-7: 'Doe']
    A --> D[Negative Index -4 to -2: 'Do']
```

## ➕ String Concatenation

Combine strings using the **`+` operator**.[1][2]

```python
a = "John"
b = "Doe"

c = a + b
print(c)  # Output: JohnDoe

c = a + " " + b
print(c)  # Output: John Doe

c = a + "," + b
print(c)  # Output: John,Doe
```

## 🛠️ String Methods

### `len()` - String Length

Returns the **number of characters** in a string.[1]

```python
a = "John"
print(len(a))  # Output: 4
```

### `lower()` and `upper()`

Convert strings to **lowercase or uppercase** (returns new string).[2]

```python
str_val = "John"
print(str_val.lower())  # Output: john
print(str_val.upper())  # Output: JOHN
```

### `find()` - Find Substring

Returns the **index of first occurrence** or `-1` if not found.[2][1]

```python
str_val = "Python Language"

print(str_val.find("Python"))  # Output: 0
print(str_val.find("th"))      # Output: 2
print(str_val.find("xyz"))     # Output: -1
```

### `index()` - Similar to find()

Returns index but **raises error** if substring not found.[2]

```python
str_val = "Python Language"
print(str_val.index("Python"))  # Output: 0
# str_val.index("xyz")  # ❌ ValueError
```

### Validation Methods

| Method | Returns True If | Example |
|--------|----------------|---------|
| `isalnum()` | All alphanumeric characters | `"abc123".isalnum()` → True |
| `isalpha()` | All alphabetic characters | `"abc".isalpha()` → True |
| `isdigit()` | All digit characters | `"123".isdigit()` → True |
| `isnumeric()` | All numeric characters | `"123".isnumeric()` → True |

```python
str_val = "abc123"
print(str_val.isalnum())   # Output: True
print(str_val.isalpha())   # Output: False

str_val = "abc"
print(str_val.isalpha())   # Output: True

str_val = "123"
print(str_val.isdigit())   # Output: True
```

### `split()` - String to List

Splits string at specified **separator** and returns a **list**.[1][2]

```python
str_val = "banana apple orange"
new_list = str_val.split(" ")
print(new_list)  # Output: ['banana', 'apple', 'orange']

str_val = "banana,apple,orange"
new_list = str_val.split(",")
print(new_list)  # Output: ['banana', 'apple', 'orange']
```

```mermaid
flowchart LR
    A["String: 'banana apple orange'"] --> B[split by space]
    B --> C["List: ['banana', 'apple', 'orange']"]
```

### `join()` - List to String

Joins elements of an iterable with a **separator** (opposite of split).[1][2]

```python
fruit = ["banana", "apple", "orange"]

new_str = " ".join(fruit)
print(new_str)  # Output: banana apple orange

new_str = ",".join(fruit)
print(new_str)  # Output: banana,apple,orange

new_str = "***".join(fruit)
print(new_str)  # Output: banana***apple***orange
```

```mermaid
flowchart LR
    A["List: ['banana', 'apple', 'orange']"] --> B[join with space]
    B --> C["String: 'banana apple orange'"]
```

## 🎯 Practical Example: Remove Spaces

Convert a string with spaces to a string without spaces using **split() and join()**.[2][1]

```python
str_val = "Python Java JavaScript C++"

# Step 1: Split by comma and space
language = str_val.split(", ")
print(language)  # Output: ['Python', 'Java', 'JavaScript', 'C++']

# Step 2: Join with space
new_str = " ".join(language)
print(new_str)  # Output: Python Java JavaScript C++
```

## 📊 Summary Table

| Operation | Method/Operator | Example | Result |
|-----------|----------------|---------|--------|
| Indexing | `[index]` | `"Hello"` | `'H'` |
| Slicing | `[start:end]` | `"Hello"[1:4]` | `'ell'` |
| Concatenation | `+` | `"Hi" + " There"` | `'Hi There'` |
| Length | `len()` | `len("Hello")` | `5` |
| Search | `in` | `"ell" in "Hello"` | `True` |
| Split | `split()` | `"a,b".split(",")` | `['a', 'b']` |
| Join | `join()` | `" ".join(['a','b'])` | `'a b'` |

***

**Next Topics**: String problem solving and advanced string manipulation techniques 🚀[2]

[2](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/e86b07cf-c2c7-439b-af6d-7e8ce713964b/image.jpg?AWSAccessKeyId=ASIA2F3EMEYEUOBXOJUB&Signature=blmX17lH3WJUdE0WltGL3ZI8EK0%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEJ3%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJHMEUCIQDX1puFrkXWWF6%2BmYgE%2FCyBHH5amoAaxaZqNIAeKc8qUwIgbeCI0w568MfH8UqCAUmwilrv%2BuxTjK7J3i5chvxr7s8q8QQIRhABGgw2OTk3NTMzMDk3MDUiDIOJ4eI4pFz5WImRsyrOBHNaEkVy%2FQcOOZpAIPb%2BCxOPfffgOUtUUD0%2Bc3MAyMNSYGu1mG8MNQBLGs9sltU0fEZgpuV4YQi2lioG2AjQgZGtW4i475ULpsjxfiHMSILeVbFL1%2B25aqpBivVvIddej13ACKfSsli%2FzzeyahNatgrBZZZdwgvx2GiVFISUaSXRTHLwLJBIozHHWeWx0adyObeftV02VMXeNbTnbzMa6uzmfjYo7Qm0DZuaMSQHsAwGerkbln2zo5zRFgsTCjDZmP16kT2DyCIySkE2vjudajJadizoU7XWNEqG5vVJ4G4VaIE%2Bx09h1yQtws18jQ2KOTGkAxYtrocOAEyX5rMR43qEEASuG19NZGcMw1OHz9kDn5jbsEfWMYFxhpi2xBkKyA6wQK%2BEOlNH7FucSQU0XosDPo8mlpJpFYs2FPk5HLQ2d2tBwbMlpJkyyp3V7TnVqD1hGcnhuWwNkOBKtkDMYCnywjTzVYdGeojSvII594eGj55PELZRaj912009vvmmrnHfFM1Iu24WeP4TeKpvCBSvjyCPtKWcI8vdqxQovPW1ttNjBmcxBFWP3h85mO8B3U8kUO%2BWllBSepk%2F94ogZHbAZvrXvvC06zBcQW7sfYq%2BHhKZ9H9%2BUoo33iTCFgHMUAqE745e6hIWPK8wN7JhHhmZhD%2FKD8L0LV%2BbxSqATdIOBxImglqjAL8PSCPm%2FAq4KtcLG4qlDFC%2Bp4%2F3fT%2Fvf0liw7KKeZRYmJgdQJrCIxAo%2FRr1nFSwNS0BmkhVBlokWRIfuqQxihNIqBvTFDF5MOXis8cGOpoBRI%2FYszDMKvaDHmvoVoLWDVH8UB0Gza16RR6QdklNyyRjNB07MUpPgRU1G2L36HpP5LBI3%2Fe3Hts23T7hAbhCqu65A6NAMeyn401ejBNX7Cmj%2FDTYsB2nNyOhS7OOztoWBydbFM4cfpGCNTYSHdAxWDUyQj%2FnXw738JN%2BUcv11FN7P8NvSTYdpnhwIfYbDVG1K4qvnYlxpx7gMA%3D%3D&Expires=1760361132)
