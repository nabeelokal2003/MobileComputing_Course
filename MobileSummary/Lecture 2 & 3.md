## **Lecture 2.1: Kotlin Basic Output**

This section explains how to display output in Kotlin.

### **Main Function (Entry Point)**

- Every Kotlin program **must** have a `main` function.
    
- Execution **starts** from the `main` function.
    
- Example:

 ```kotlin
   fun main() {
   println("Hello world!")
}
```

Output:

```nginx
Hello world!
```

### **Print() vs Println()**

- `print()`: Outputs text **without a newline**.
    
- `println()`: Outputs text and **moves the cursor to the next line**.
    

#### **Example: Difference between `print()` and `println()`**

```kotlin
fun main() {
    println("Hello, World!")
    println("Hello, Kotlin!")
}
```

Output:

```kotlin
Hello, World!
Hello, Kotlin!
```

```kotlin
fun main() {
    print("Hello, World!")
    print("Hello, Kotlin!")
}
```

Output:

```kotlin
Hello, World!Hello, Kotlin!
```

## **Lecture 3: Variables and Data Types in Kotlin**

### **Comments in Kotlin**

- Used for **code documentation** and are ignored by the compiler.
    
- **Single-line comment:** `//`
    
- **Multi-line comment:** `/* ... */`
    
- **Kotlin supports nested comments** (unlike some other languages).
    

### **Variables in Kotlin**

- A **variable** is a container for storing values.
    
- Kotlin has **two types of variables**:
    
    1. **Mutable (`var`)**: Can change its value.
        
    2. **Immutable (`val`)**: Value **cannot be changed** after assignment.
        

#### **Examples: Mutable vs Immutable Variables**

```kotlin
val number = 1
number = 2  // Error: val cannot be reassigned
```

```kotlin
var number = 1
number = 2  // Works fine
```

### **Printing Variables**

- Use `$variableName` to print variables inside strings.
    
- Use `${expression}` for **calculations inside print statements**.
    

#### **Example: Using `$` in Strings**

```kotlin
fun main() {
    val userName = "Florian"
    var age = 28
    println("Hello, world! My name is $userName. I am $age years old. In 2 years, I'll be ${age + 2}.")
}
```

Output:

```mathematica
Hello, world! My name is Florian. I am 28 years old. In 2 years, I'll be 30.
```

### **Identifiers in Kotlin**

- **Valid identifiers**:
    
    - Must start with a **letter or underscore**.
        
    - Cannot contain spaces or special characters (`@, $, #`).
        
    - Are **case-sensitive** (`Score` and `score` are different).
        
    - Example of a valid identifier: `highestScore`
        
    - Example of an invalid identifier: `2number` (cannot start with a number).
        

### **Kotlin Keywords**

- **Reserved words** that **cannot be used as identifiers**.
    
- Examples: `fun`, `class`, `val`, `var`.
    

### **Data Types in Kotlin**

1. **Numbers**
    
    - **Integer Types**:
        
        - `Byte` (8-bit)
            
        - `Short` (16-bit)
            
        - `Int` (32-bit)
            
        - `Long` (64-bit)
            
    - **Floating-Point Types**:
        
        - `Float` (32-bit)
            
        - `Double` (64-bit)
            
2. **Booleans**: Can be `true` or `false`.
    
3. **Characters**: Declared using single quotes (`'A'`).
    
4. **Strings**: Declared using `"..."`, immutable.
    

#### **Example: Numeric Types**

```kotlin
val myInt = 1000
val myLong = 1000L  // 'L' for Long
val myFloat = 126.78f  // 'f' for Float
val myDouble = 325.49
```

#### **Example: Boolean & Character**

```kotlin
val isKotlinFun = true
val letter = 'K'
```

### **Type Inference in Kotlin**

- **Explicitly specifying types is optional** in many cases.
    
- Example:

```kotlin
  val greeting = "Hello, World"  // Type inferred as String
  val year = 2025  // Type inferred as Int
```

- But if no initial value is assigned, the type **must** be specified:

```kotlin
var language: String
language = "French"
```

---

## **Conclusion**

This document provides **a beginner-friendly introduction** to Kotlin, covering:

- **Basic output (`print` vs `println`)**
    
- **Comments and variables (`var` and `val`)**
    
- **Data types (Numbers, Strings, Booleans, Characters)**
    
- **Type inference (letting Kotlin guess the type)**
    
- **String formatting using `$variableName` and `${expression}`**