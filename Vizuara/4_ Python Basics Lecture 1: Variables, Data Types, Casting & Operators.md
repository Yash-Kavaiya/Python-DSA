Based on the provided transcription about Python introduction, here are comprehensive GitHub-flavored markdown notes:

# 🐍 Introduction to Python: Basics, Advantages, Code Execution, Interpreter & REPL

## 📋 Table of Contents
- [What is Python?](#what-is-python)
- [Advantages of Python](#advantages-of-python)
- [Python Code Execution Process](#python-code-execution-process)
- [Python Interpreter Architecture](#python-interpreter-architecture)
- [Understanding REPL](#understanding-repl)
- [Key Concepts Summary](#key-concepts-summary)

***

## 🎯 What is Python?

**Python** is an **interpreted**, **object-oriented**, **high-level programming language** with **dynamic semantics**.

### 🔍 Key Characteristics

| Characteristic | Description |
|----------------|-------------|
| **Interpreted** | Executes code line by line, providing immediate feedback |
| **Object-Oriented** | Everything in Python is treated as an object |
| **Dynamic Semantics** | No need to declare variable types explicitly (unlike C, C++, Java) |
| **Creator** | Guido van Rossum |
| **Release Year** | 1991 |

### 🚀 Common Applications
- 🌐 **Web Applications**
- 💾 **Software Development** 
- 📊 **Data Science**
- 🤖 **Machine Learning**
- 🧠 **Artificial Intelligence**

***

## ⭐ Advantages of Python

| Advantage | Details |
|-----------|---------|
| 🌍 **Platform Independent** | Works on Windows, Mac, Linux, Raspberry Pi |
| 💰 **Free to Use** | No licensing fees required |
| 📝 **Easy Syntax** | Reads like English, requires fewer lines of code |
| 🐛 **Easy Debugging** | Interpreted nature makes debugging straightforward |
| 🔧 **Flexible Programming** | Supports both procedural and object-oriented approaches |
| 📚 **Rich Standard Library** | Extensive libraries for ML, data science, analytics, visualization |

***

## ⚙️ Python Code Execution Process

```mermaid
flowchart LR
    A[intro.py<br/>Source File] --> B[Python Interpreter]
    B --> C[Compiler]
    B --> D[PVM]
    C --> E[Bytecode<br/>.pyc file]
    E --> D
    D --> F[Machine Code<br/>0101...]
    F --> G[CPU]
    G --> H[Output]
    
    style A fill:#e1f5fe
    style E fill:#fff3e0
    style F fill:#f3e5f5
    style H fill:#e8f5e8
```

### 📋 Execution Steps

#### **Step 1: Syntax & Indentation Check** ✅
- Compiler checks for **indentation errors**
- Validates **syntax** (missing colons, parentheses, etc.)
- ⚠️ **If errors found**: Execution stops, no bytecode generated

#### **Step 2: Tokenization** 🔤
- Source code divided into **smaller chunks** called **tokens**
- Lexical tokens converted into **bytecode**

#### **Step 3: PVM Processing** ⚡
- **PVM (Python Virtual Machine)** converts bytecode into **executable code**
- Generates **binary code** (0s and 1s)
- Passes to **CPU** for execution

***

## 🏗️ Python Interpreter Architecture

```mermaid
graph TB
    subgraph "Python Interpreter (CPython)"
        A[Compiler] 
        B[PVM - Python Virtual Machine]
    end
    
    C[Source Code<br/>intro.py] --> A
    A --> D[Bytecode<br/>.pyc]
    D --> B
    B --> E[Machine Code<br/>01010101]
    E --> F[System/CPU]
    F --> G[Output]
    
    style A fill:#ffcdd2
    style B fill:#c8e6c9
    style D fill:#fff9c4
    style E fill:#e1bee7
```

### 🔧 Core Components

| Component | Function | Written In |
|-----------|----------|------------|
| **CPython** | Main Python interpreter | C Programming Language |
| **Compiler** | Converts source to bytecode | Part of interpreter |
| **PVM** | Runtime engine for bytecode execution | Part of interpreter |

***

## 🔄 Understanding REPL

**REPL** stands for **Read**, **Evaluate**, **Print**, **Loop** 💡

### 🎮 REPL Process Flow

```mermaid
flowchart LR
    A[Read Input] --> B[Evaluate Expression]
    B --> C[Print Result]
    C --> D[Loop Back]
    D --> A
    
    style A fill:#e3f2fd
    style B fill:#fff3e0
    style C fill:#e8f5e8
    style D fill:#fce4ec
```

### 📝 REPL Examples

```python
# Access Python REPL
$ python3

# Example 1: Simple number
>>> 8
8

# Example 2: Arithmetic operation
>>> 8 + 10
18

# Example 3: Multiplication
>>> 30 * 2
60

# Example 4: Modulo operation
>>> 20 % 3
2
```

### 🔄 REPL Workflow Breakdown

| Step | Action | Example |
|------|--------|---------|
| **Read** 📖 | Takes user input | `8 + 10` |
| **Evaluate** ⚡ | Processes the expression | Calculates: 8 + 10 = 18 |
| **Print** 🖨️ | Displays the result | Shows: `18` |
| **Loop** 🔄 | Ready for next input | Waits for new command |

***

## 📚 Key Concepts Summary

<details>
<summary><strong>🔍 Important Terms Glossary</strong></summary>

- **Interpreted Language**: Code executed line by line, not compiled beforehand
- **Dynamic Semantics**: Variable types determined at runtime, not declaration
- **Object-Oriented**: Everything treated as objects with properties and methods
- **Bytecode**: Intermediate code format between source and machine code
- **PVM**: Python Virtual Machine that executes bytecode
- **REPL**: Interactive shell for immediate code execution and testing

</details>

### ⚡ Quick Facts

> 🎯 **Python's Philosophy**: Write code that reads like English  
> 🚀 **Development Speed**: Fewer lines of code = faster development  
> 🔧 **Flexibility**: Supports multiple programming paradigms  
> 📦 **Rich Ecosystem**: Extensive library support for any task  

***

## 🎓 Learning Path Recommendations

```mermaid
mindmap
  root((Python Mastery))
    Fundamentals
      Variables & Data Types
      Operators
      Control Structures
    Intermediate
      Functions
      Classes & Objects
      File Handling
    Advanced
      Libraries & Frameworks
      Data Science Tools
      Web Development
```

### 🛠️ Next Steps
1. **Practice REPL commands** for immediate feedback
2. **Write simple Python scripts** to understand execution flow
3. **Explore Python's standard library** for built-in functionality
4. **Start with small projects** to apply learned concepts

***

*💡 **Pro Tip**: Use Python's REPL extensively for quick testing and learning - it's one of Python's most powerful features for beginners!* 🚀

[1](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/ebe33608-3c24-4b4a-9af2-1dd289c4e6d8/screenshot.jpg?AWSAccessKeyId=ASIA2F3EMEYE7L7UWE7Q&Signature=5DtXXHfMvv14vmMSofWNhubgb74%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIf%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJFMEMCIFCVaxqj5WM85LcvrAa7uToR%2FZqIyMiIpIIq1ywujKJwAh8Fekb8Az1SIABH4PyNVNqI8tvObyjjZXc%2FeCTRL%2FiDKvEECDAQARoMNjk5NzUzMzA5NzA1IgzOPk3F5bPQyt34zYAqzgSkPZfESv7rAB6GwrxYTxXKXZ6Fr3TGuGsml%2Bi%2FYOYXUY%2BaeoCZ%2FCyiKMlIT1OEvP%2Fjji3J6f9wVYTJWeipc6GQlfXGGtki%2FPcZxPe8qkjHSC9suxixysNhzNrkbuCZNa5yQXCF1jBTgEai4kWjyOLK%2BVgiPjlcNOIcPWJkbAo6xgQ7f9%2B%2B8fv7a6tCaMJeDuh8WP4%2B7PT6b8utz7seIiX2%2FZvMsi2%2B6EwaX9NgVBHDlctLV80zyyqKVqHC0nuISaq2CEh1nlHabjK7tbPR6sig5i2tPVC20IysG0ynIfOcl7pQwpJj1YYPrSH2DHMmGHq%2F9dSscWo4TMgIUjmCzw1iPy%2FZUITPB1b%2BhL1lWTTmYg7DKvQr7VWz3MLcg5ZL6fxsphpxlkxLmyClF9abJaR8tZ4RZ7SwYVLBaCG%2Fgc0nq0DluekJUahVPjveqsnsuxnxkhtGjuL6hgWzRf1CjiWr4lKDiaMlpigXkHAsN15jugIUQ12QgdrUnC9Fq0rLSorMGPXE%2FOoIe%2F9EzMz8Lq%2B0ED8DAHWl6MXTWRPREhTZSUi7NXNrBjQCFDprDRh9n1K2ONv8OLSRzuGIkrcXDSvnGbY19aGV6YjIcYEw5C%2FelXiI%2FWv0WnCCN1WDXTfjrpyXbjdCvpmH3wvFyyCZ6%2FGAIX4U%2Fn26LV%2BN%2BiYcZiIhq%2FnnqqZqjQY8vBskcbGC9knpNh6oFKoENVhBdLtv1PibjfzAZ3dWKSwnsgOGUT%2FpFBg%2B1iVQn1yfpmDwsXuxHdRuUo0499wlkh6PbDeWWjD5%2FK7HBjqcAfy6AIa%2FuFzorOzdIaIkxia%2Bj8%2F9fTEDL0yzeIViB0r4joP5n4I9OTQHuwHOLrkFmEBFcpzHI9UuIAhFeP%2FkrnLFqQI3z39iTAlXjE5A7RhoYakDOvJLhGL34Q7AU7VPJxVOJPaGifDCmo0SNmzLT5fm9%2F3Azt2PbLyKgbnjCUp%2B9qJGaVe%2BmGECKWInCqlvwotGwCGXLNtdpvn00A%3D%3D&Expires=1760282746)
[2](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/1dd7ed07-0e3c-46bb-97f6-331d5b65998d/screenshot.jpg?AWSAccessKeyId=ASIA2F3EMEYE7L7UWE7Q&Signature=TmpdcBfM5PeGhc4hJS5R4FhbLFA%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIf%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJFMEMCIFCVaxqj5WM85LcvrAa7uToR%2FZqIyMiIpIIq1ywujKJwAh8Fekb8Az1SIABH4PyNVNqI8tvObyjjZXc%2FeCTRL%2FiDKvEECDAQARoMNjk5NzUzMzA5NzA1IgzOPk3F5bPQyt34zYAqzgSkPZfESv7rAB6GwrxYTxXKXZ6Fr3TGuGsml%2Bi%2FYOYXUY%2BaeoCZ%2FCyiKMlIT1OEvP%2Fjji3J6f9wVYTJWeipc6GQlfXGGtki%2FPcZxPe8qkjHSC9suxixysNhzNrkbuCZNa5yQXCF1jBTgEai4kWjyOLK%2BVgiPjlcNOIcPWJkbAo6xgQ7f9%2B%2B8fv7a6tCaMJeDuh8WP4%2B7PT6b8utz7seIiX2%2FZvMsi2%2B6EwaX9NgVBHDlctLV80zyyqKVqHC0nuISaq2CEh1nlHabjK7tbPR6sig5i2tPVC20IysG0ynIfOcl7pQwpJj1YYPrSH2DHMmGHq%2F9dSscWo4TMgIUjmCzw1iPy%2FZUITPB1b%2BhL1lWTTmYg7DKvQr7VWz3MLcg5ZL6fxsphpxlkxLmyClF9abJaR8tZ4RZ7SwYVLBaCG%2Fgc0nq0DluekJUahVPjveqsnsuxnxkhtGjuL6hgWzRf1CjiWr4lKDiaMlpigXkHAsN15jugIUQ12QgdrUnC9Fq0rLSorMGPXE%2FOoIe%2F9EzMz8Lq%2B0ED8DAHWl6MXTWRPREhTZSUi7NXNrBjQCFDprDRh9n1K2ONv8OLSRzuGIkrcXDSvnGbY19aGV6YjIcYEw5C%2FelXiI%2FWv0WnCCN1WDXTfjrpyXbjdCvpmH3wvFyyCZ6%2FGAIX4U%2Fn26LV%2BN%2BiYcZiIhq%2FnnqqZqjQY8vBskcbGC9knpNh6oFKoENVhBdLtv1PibjfzAZ3dWKSwnsgOGUT%2FpFBg%2B1iVQn1yfpmDwsXuxHdRuUo0499wlkh6PbDeWWjD5%2FK7HBjqcAfy6AIa%2FuFzorOzdIaIkxia%2Bj8%2F9fTEDL0yzeIViB0r4joP5n4I9OTQHuwHOLrkFmEBFcpzHI9UuIAhFeP%2FkrnLFqQI3z39iTAlXjE5A7RhoYakDOvJLhGL34Q7AU7VPJxVOJPaGifDCmo0SNmzLT5fm9%2F3Azt2PbLyKgbnjCUp%2B9qJGaVe%2BmGECKWInCqlvwotGwCGXLNtdpvn00A%3D%3D&Expires=1760282746)
[3](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/821daf72-5349-403d-a224-980d3fa8d80d/screenshot.jpg?AWSAccessKeyId=ASIA2F3EMEYE7L7UWE7Q&Signature=kLChc7bUKFR1%2Bwoj5yfTPhuo%2FwY%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIf%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJFMEMCIFCVaxqj5WM85LcvrAa7uToR%2FZqIyMiIpIIq1ywujKJwAh8Fekb8Az1SIABH4PyNVNqI8tvObyjjZXc%2FeCTRL%2FiDKvEECDAQARoMNjk5NzUzMzA5NzA1IgzOPk3F5bPQyt34zYAqzgSkPZfESv7rAB6GwrxYTxXKXZ6Fr3TGuGsml%2Bi%2FYOYXUY%2BaeoCZ%2FCyiKMlIT1OEvP%2Fjji3J6f9wVYTJWeipc6GQlfXGGtki%2FPcZxPe8qkjHSC9suxixysNhzNrkbuCZNa5yQXCF1jBTgEai4kWjyOLK%2BVgiPjlcNOIcPWJkbAo6xgQ7f9%2B%2B8fv7a6tCaMJeDuh8WP4%2B7PT6b8utz7seIiX2%2FZvMsi2%2B6EwaX9NgVBHDlctLV80zyyqKVqHC0nuISaq2CEh1nlHabjK7tbPR6sig5i2tPVC20IysG0ynIfOcl7pQwpJj1YYPrSH2DHMmGHq%2F9dSscWo4TMgIUjmCzw1iPy%2FZUITPB1b%2BhL1lWTTmYg7DKvQr7VWz3MLcg5ZL6fxsphpxlkxLmyClF9abJaR8tZ4RZ7SwYVLBaCG%2Fgc0nq0DluekJUahVPjveqsnsuxnxkhtGjuL6hgWzRf1CjiWr4lKDiaMlpigXkHAsN15jugIUQ12QgdrUnC9Fq0rLSorMGPXE%2FOoIe%2F9EzMz8Lq%2B0ED8DAHWl6MXTWRPREhTZSUi7NXNrBjQCFDprDRh9n1K2ONv8OLSRzuGIkrcXDSvnGbY19aGV6YjIcYEw5C%2FelXiI%2FWv0WnCCN1WDXTfjrpyXbjdCvpmH3wvFyyCZ6%2FGAIX4U%2Fn26LV%2BN%2BiYcZiIhq%2FnnqqZqjQY8vBskcbGC9knpNh6oFKoENVhBdLtv1PibjfzAZ3dWKSwnsgOGUT%2FpFBg%2B1iVQn1yfpmDwsXuxHdRuUo0499wlkh6PbDeWWjD5%2FK7HBjqcAfy6AIa%2FuFzorOzdIaIkxia%2Bj8%2F9fTEDL0yzeIViB0r4joP5n4I9OTQHuwHOLrkFmEBFcpzHI9UuIAhFeP%2FkrnLFqQI3z39iTAlXjE5A7RhoYakDOvJLhGL34Q7AU7VPJxVOJPaGifDCmo0SNmzLT5fm9%2F3Azt2PbLyKgbnjCUp%2B9qJGaVe%2BmGECKWInCqlvwotGwCGXLNtdpvn00A%3D%3D&Expires=1760282746)
[4](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/615b7f51-bb2e-4820-8733-fe85e667f381/screenshot.jpg?AWSAccessKeyId=ASIA2F3EMEYE7L7UWE7Q&Signature=oOtkAxlJFGzN1OkJwZ1J6vdzzqY%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIf%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJFMEMCIFCVaxqj5WM85LcvrAa7uToR%2FZqIyMiIpIIq1ywujKJwAh8Fekb8Az1SIABH4PyNVNqI8tvObyjjZXc%2FeCTRL%2FiDKvEECDAQARoMNjk5NzUzMzA5NzA1IgzOPk3F5bPQyt34zYAqzgSkPZfESv7rAB6GwrxYTxXKXZ6Fr3TGuGsml%2Bi%2FYOYXUY%2BaeoCZ%2FCyiKMlIT1OEvP%2Fjji3J6f9wVYTJWeipc6GQlfXGGtki%2FPcZxPe8qkjHSC9suxixysNhzNrkbuCZNa5yQXCF1jBTgEai4kWjyOLK%2BVgiPjlcNOIcPWJkbAo6xgQ7f9%2B%2B8fv7a6tCaMJeDuh8WP4%2B7PT6b8utz7seIiX2%2FZvMsi2%2B6EwaX9NgVBHDlctLV80zyyqKVqHC0nuISaq2CEh1nlHabjK7tbPR6sig5i2tPVC20IysG0ynIfOcl7pQwpJj1YYPrSH2DHMmGHq%2F9dSscWo4TMgIUjmCzw1iPy%2FZUITPB1b%2BhL1lWTTmYg7DKvQr7VWz3MLcg5ZL6fxsphpxlkxLmyClF9abJaR8tZ4RZ7SwYVLBaCG%2Fgc0nq0DluekJUahVPjveqsnsuxnxkhtGjuL6hgWzRf1CjiWr4lKDiaMlpigXkHAsN15jugIUQ12QgdrUnC9Fq0rLSorMGPXE%2FOoIe%2F9EzMz8Lq%2B0ED8DAHWl6MXTWRPREhTZSUi7NXNrBjQCFDprDRh9n1K2ONv8OLSRzuGIkrcXDSvnGbY19aGV6YjIcYEw5C%2FelXiI%2FWv0WnCCN1WDXTfjrpyXbjdCvpmH3wvFyyCZ6%2FGAIX4U%2Fn26LV%2BN%2BiYcZiIhq%2FnnqqZqjQY8vBskcbGC9knpNh6oFKoENVhBdLtv1PibjfzAZ3dWKSwnsgOGUT%2FpFBg%2B1iVQn1yfpmDwsXuxHdRuUo0499wlkh6PbDeWWjD5%2FK7HBjqcAfy6AIa%2FuFzorOzdIaIkxia%2Bj8%2F9fTEDL0yzeIViB0r4joP5n4I9OTQHuwHOLrkFmEBFcpzHI9UuIAhFeP%2FkrnLFqQI3z39iTAlXjE5A7RhoYakDOvJLhGL34Q7AU7VPJxVOJPaGifDCmo0SNmzLT5fm9%2F3Azt2PbLyKgbnjCUp%2B9qJGaVe%2BmGECKWInCqlvwotGwCGXLNtdpvn00A%3D%3D&Expires=1760282746)
[5](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/cf679fea-e074-4eb2-9c5c-17da795954c1/screenshot.jpg?AWSAccessKeyId=ASIA2F3EMEYE7L7UWE7Q&Signature=FfIsoMvaQbq6YIKKjobVFeAFBxI%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIf%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJFMEMCIFCVaxqj5WM85LcvrAa7uToR%2FZqIyMiIpIIq1ywujKJwAh8Fekb8Az1SIABH4PyNVNqI8tvObyjjZXc%2FeCTRL%2FiDKvEECDAQARoMNjk5NzUzMzA5NzA1IgzOPk3F5bPQyt34zYAqzgSkPZfESv7rAB6GwrxYTxXKXZ6Fr3TGuGsml%2Bi%2FYOYXUY%2BaeoCZ%2FCyiKMlIT1OEvP%2Fjji3J6f9wVYTJWeipc6GQlfXGGtki%2FPcZxPe8qkjHSC9suxixysNhzNrkbuCZNa5yQXCF1jBTgEai4kWjyOLK%2BVgiPjlcNOIcPWJkbAo6xgQ7f9%2B%2B8fv7a6tCaMJeDuh8WP4%2B7PT6b8utz7seIiX2%2FZvMsi2%2B6EwaX9NgVBHDlctLV80zyyqKVqHC0nuISaq2CEh1nlHabjK7tbPR6sig5i2tPVC20IysG0ynIfOcl7pQwpJj1YYPrSH2DHMmGHq%2F9dSscWo4TMgIUjmCzw1iPy%2FZUITPB1b%2BhL1lWTTmYg7DKvQr7VWz3MLcg5ZL6fxsphpxlkxLmyClF9abJaR8tZ4RZ7SwYVLBaCG%2Fgc0nq0DluekJUahVPjveqsnsuxnxkhtGjuL6hgWzRf1CjiWr4lKDiaMlpigXkHAsN15jugIUQ12QgdrUnC9Fq0rLSorMGPXE%2FOoIe%2F9EzMz8Lq%2B0ED8DAHWl6MXTWRPREhTZSUi7NXNrBjQCFDprDRh9n1K2ONv8OLSRzuGIkrcXDSvnGbY19aGV6YjIcYEw5C%2FelXiI%2FWv0WnCCN1WDXTfjrpyXbjdCvpmH3wvFyyCZ6%2FGAIX4U%2Fn26LV%2BN%2BiYcZiIhq%2FnnqqZqjQY8vBskcbGC9knpNh6oFKoENVhBdLtv1PibjfzAZ3dWKSwnsgOGUT%2FpFBg%2B1iVQn1yfpmDwsXuxHdRuUo0499wlkh6PbDeWWjD5%2FK7HBjqcAfy6AIa%2FuFzorOzdIaIkxia%2Bj8%2F9fTEDL0yzeIViB0r4joP5n4I9OTQHuwHOLrkFmEBFcpzHI9UuIAhFeP%2FkrnLFqQI3z39iTAlXjE5A7RhoYakDOvJLhGL34Q7AU7VPJxVOJPaGifDCmo0SNmzLT5fm9%2F3Azt2PbLyKgbnjCUp%2B9qJGaVe%2BmGECKWInCqlvwotGwCGXLNtdpvn00A%3D%3D&Expires=1760282746)
[6](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/99121bc0-1b68-4c6e-b98f-840507b21842/screenshot.jpg?AWSAccessKeyId=ASIA2F3EMEYE7L7UWE7Q&Signature=O0i%2BJ7fkyiYJygTc6FgU%2BW0yuUI%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIf%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJFMEMCIFCVaxqj5WM85LcvrAa7uToR%2FZqIyMiIpIIq1ywujKJwAh8Fekb8Az1SIABH4PyNVNqI8tvObyjjZXc%2FeCTRL%2FiDKvEECDAQARoMNjk5NzUzMzA5NzA1IgzOPk3F5bPQyt34zYAqzgSkPZfESv7rAB6GwrxYTxXKXZ6Fr3TGuGsml%2Bi%2FYOYXUY%2BaeoCZ%2FCyiKMlIT1OEvP%2Fjji3J6f9wVYTJWeipc6GQlfXGGtki%2FPcZxPe8qkjHSC9suxixysNhzNrkbuCZNa5yQXCF1jBTgEai4kWjyOLK%2BVgiPjlcNOIcPWJkbAo6xgQ7f9%2B%2B8fv7a6tCaMJeDuh8WP4%2B7PT6b8utz7seIiX2%2FZvMsi2%2B6EwaX9NgVBHDlctLV80zyyqKVqHC0nuISaq2CEh1nlHabjK7tbPR6sig5i2tPVC20IysG0ynIfOcl7pQwpJj1YYPrSH2DHMmGHq%2F9dSscWo4TMgIUjmCzw1iPy%2FZUITPB1b%2BhL1lWTTmYg7DKvQr7VWz3MLcg5ZL6fxsphpxlkxLmyClF9abJaR8tZ4RZ7SwYVLBaCG%2Fgc0nq0DluekJUahVPjveqsnsuxnxkhtGjuL6hgWzRf1CjiWr4lKDiaMlpigXkHAsN15jugIUQ12QgdrUnC9Fq0rLSorMGPXE%2FOoIe%2F9EzMz8Lq%2B0ED8DAHWl6MXTWRPREhTZSUi7NXNrBjQCFDprDRh9n1K2ONv8OLSRzuGIkrcXDSvnGbY19aGV6YjIcYEw5C%2FelXiI%2FWv0WnCCN1WDXTfjrpyXbjdCvpmH3wvFyyCZ6%2FGAIX4U%2Fn26LV%2BN%2BiYcZiIhq%2FnnqqZqjQY8vBskcbGC9knpNh6oFKoENVhBdLtv1PibjfzAZ3dWKSwnsgOGUT%2FpFBg%2B1iVQn1yfpmDwsXuxHdRuUo0499wlkh6PbDeWWjD5%2FK7HBjqcAfy6AIa%2FuFzorOzdIaIkxia%2Bj8%2F9fTEDL0yzeIViB0r4joP5n4I9OTQHuwHOLrkFmEBFcpzHI9UuIAhFeP%2FkrnLFqQI3z39iTAlXjE5A7RhoYakDOvJLhGL34Q7AU7VPJxVOJPaGifDCmo0SNmzLT5fm9%2F3Azt2PbLyKgbnjCUp%2B9qJGaVe%2BmGECKWInCqlvwotGwCGXLNtdpvn00A%3D%3D&Expires=1760282746)
[7](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/10242390/ac990205-b81f-4bf0-997d-c8d5dc64fa5d/screenshot.jpg?AWSAccessKeyId=ASIA2F3EMEYE7L7UWE7Q&Signature=NopFCu9ndYxkMwVVx5ESAwEMdGs%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEIf%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJFMEMCIFCVaxqj5WM85LcvrAa7uToR%2FZqIyMiIpIIq1ywujKJwAh8Fekb8Az1SIABH4PyNVNqI8tvObyjjZXc%2FeCTRL%2FiDKvEECDAQARoMNjk5NzUzMzA5NzA1IgzOPk3F5bPQyt34zYAqzgSkPZfESv7rAB6GwrxYTxXKXZ6Fr3TGuGsml%2Bi%2FYOYXUY%2BaeoCZ%2FCyiKMlIT1OEvP%2Fjji3J6f9wVYTJWeipc6GQlfXGGtki%2FPcZxPe8qkjHSC9suxixysNhzNrkbuCZNa5yQXCF1jBTgEai4kWjyOLK%2BVgiPjlcNOIcPWJkbAo6xgQ7f9%2B%2B8fv7a6tCaMJeDuh8WP4%2B7PT6b8utz7seIiX2%2FZvMsi2%2B6EwaX9NgVBHDlctLV80zyyqKVqHC0nuISaq2CEh1nlHabjK7tbPR6sig5i2tPVC20IysG0ynIfOcl7pQwpJj1YYPrSH2DHMmGHq%2F9dSscWo4TMgIUjmCzw1iPy%2FZUITPB1b%2BhL1lWTTmYg7DKvQr7VWz3MLcg5ZL6fxsphpxlkxLmyClF9abJaR8tZ4RZ7SwYVLBaCG%2Fgc0nq0DluekJUahVPjveqsnsuxnxkhtGjuL6hgWzRf1CjiWr4lKDiaMlpigXkHAsN15jugIUQ12QgdrUnC9Fq0rLSorMGPXE%2FOoIe%2F9EzMz8Lq%2B0ED8DAHWl6MXTWRPREhTZSUi7NXNrBjQCFDprDRh9n1K2ONv8OLSRzuGIkrcXDSvnGbY19aGV6YjIcYEw5C%2FelXiI%2FWv0WnCCN1WDXTfjrpyXbjdCvpmH3wvFyyCZ6%2FGAIX4U%2Fn26LV%2BN%2BiYcZiIhq%2FnnqqZqjQY8vBskcbGC9knpNh6oFKoENVhBdLtv1PibjfzAZ3dWKSwnsgOGUT%2FpFBg%2B1iVQn1yfpmDwsXuxHdRuUo0499wlkh6PbDeWWjD5%2FK7HBjqcAfy6AIa%2FuFzorOzdIaIkxia%2Bj8%2F9fTEDL0yzeIViB0r4joP5n4I9OTQHuwHOLrkFmEBFcpzHI9UuIAhFeP%2FkrnLFqQI3z39iTAlXjE5A7RhoYakDOvJLhGL34Q7AU7VPJxVOJPaGifDCmo0SNmzLT5fm9%2F3Azt2PbLyKgbnjCUp%2B9qJGaVe%2BmGECKWInCqlvwotGwCGXLNtdpvn00A%3D%3D&Expires=1760282746)
[8](https://www.youtube.com/watch?v=Logaf1WUakk&list=PLPTV0NXA_ZSgHj4a9CE1KLSarhkjocecO&index=4)
