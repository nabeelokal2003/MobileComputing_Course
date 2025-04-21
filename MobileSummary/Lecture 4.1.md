### **Summary of the File: Lec4.1_Final_operations in Kotlin.pdf**

This document provides a **detailed explanation of operators in Kotlin**, including arithmetic, comparison, assignment, and logical operations. It also covers **escape characters, string operations, and operator precedence**.

---

## **1. Escape Characters in Kotlin**

Kotlin supports various escape characters for formatting strings:

|Escape Character|Meaning|
|---|---|
|`\t`|Tab|
|`\b`|Backspace|
|`\n`|New Line|
|`\r`|Carriage Return|
|`\'`|Single Quote|
|`\"`|Double Quote|
|`\\`|Backslash|
|`\$`|Dollar Sign|

### **Example: Using Escape Characters**

```kotlin
fun main() {
    var myEscapedString = "Hello Reader,\nWelcome to my Blog"
    println(myEscapedString)
}
```

**Output:**

```css
Hello Reader,
Welcome to my Blog
```

---

## **2. Raw Strings vs Escaped Strings**

- **Escaped Strings**: Strings with escape sequences (`\n`, `\t`).
    
- **Raw Strings**: Multi-line strings **without escape sequences**, declared using triple quotes (`""" """`).
    

### **Example: Raw String**

```kotlin
var myMultilineRawString = """
The Quick Brown Fox
Jumped Over a Lazy Dog.
"""
println(myMultilineRawString)
```

**Output:**

```mathematica
The Quick Brown Fox
Jumped Over a Lazy Dog.
```

---

## **3. Arithmetic Operations in Kotlin**

Kotlin supports **basic arithmetic operators**:

| Operator | Description         |
| -------- | ------------------- |
| `+`      | Addition            |
| `-`      | Subtraction         |
| `*`      | Multiplication      |
| `/`      | Division            |
| `%`      | Modulus (Remainder) |

### **Example: Arithmetic Operations**

```kotlin
val number1 = 12.5
val number2 = 3.5
var result: Double

result = number1 + number2
println("number1 + number2 = $result")
```

**Output:**

```nginx
number1 + number2 = 16.0
```

---

## **4. How Operators Work in Kotlin**

- Kotlin treats **everything as an object**, even basic data types (`Int`, `Char`, `Boolean`).
    
- Operators are actually **function calls** in Kotlin.
    
    - Example: `a + b` is internally called as `a.plus(b)`.
        

### **Example: Using Function Calls Instead of Operators**

```kotlin
println(2.plus(71).plus(233).minus(13))
```

---

## **5. Comparison and Equality Operators**

Comparison operators are used to compare two values.

|Operator|Description|
|---|---|
|`==`|Equal to|
|`!=`|Not equal to|
|`<`|Less than|
|`>`|Greater than|
|`<=`|Less than or equal to|
|`>=`|Greater than or equal to|

### **Referential Equality (`===` vs `!==`)**

- `===` compares **references** (if two objects point to the same memory location).
    
- `!==` checks **if references are different**.
    

### **Example: Comparison Operators**

```kotlin
fun main() {
    var a = 10
    var b = 20
    var isALessThanB = a < b  // true
    println("isALessThanB = $isALessThanB")
}
```

**Output:**

```ini
isALessThanB = true
```

---

## **6. Assignment Operators**

- Assignment operators are used to assign values to variables.
    
- Shorthand versions exist for common operations.
    

|Operator|Equivalent To|
|---|---|
|`+=`|`a = a + b`|
|`-=`|`a = a - b`|
|`*=`|`a = a * b`|
|`/=`|`a = a / b`|
|`%=`|`a = a % b`|

### **Example: Assignment Operator**

```kotlin
fun main() {
    var number = 12
    number *= 5  // number = number * 5
    println("number = $number")
}
```

**Output:**

```ini
number = 60
```

---

## **7. Increment & Decrement Operators**

Kotlin supports:

- **Pre-increment (`++a`)**: Increases `a` before using it.
    
- **Post-increment (`a++`)**: Uses `a`, then increases it.
    
- **Pre-decrement (`--a`)**: Decreases `a` before using it.
    
- **Post-decrement (`a--`)**: Uses `a`, then decreases it.
    

### **Example: Increment & Decrement**

```kotlin
var variable_one = 2
var variable_two = ++variable_one  // Pre-increment
println("variable_one = $variable_one")
println("variable_two = $variable_two")
```

**Output:**

```ini
variable_one = 3
variable_two = 3
```

---

## **8. Logical Operators**

Logical operators work with Boolean values.

|Operator|Description|
|---|---|
|`&&`|Logical AND|
|`||
|`!`|Logical NOT|

### **Example: Logical Operators**

```kotlin
fun main() {
    var a = true
    var b = false

    println(a && b)  // false
    println(a || b)  // true
}
```

**Output:**

```arduino
false
true
```

---

## **9. String Operations**

- **Concatenation (`+` operator)**
    
- **Interpolation (`$variable` inside a string)**
    

### **Example: String Concatenation**

```kotlin
fun main() {
    var firstName = "Rajeev"
    var lastName = "Singh"
    var fullName = firstName + " " + lastName
    println(fullName)
}
```

**Output:**

```nginx
Rajeev Singh
```

---

## **10. Operator Precedence (Priority Order)**

- Operators are evaluated based on **precedence**.
    
- Multiplication (`*`) happens before addition (`+`).
    

|Level|Operators|Associativity|
|---|---|---|
|16|`()`|Left to Right|
|15|`++`, `--`|Not Associative|
|14|`+`, `-` (Unary)|Right to Left|
|12|`*`, `/`, `%`|Left to Right|
|11|`+`, `-` (Binary)|Left to Right|
|9|`<`, `<=`, `>`, `>=`|Not Associative|
|8|`==`, `!=`|Left to Right|
|4|`&&`|Left to Right|
|3|`||
|1|`=`, `+=`, `-=`, `*=`, `/=`, `%=`|Right to Left|

### **Example: Operator Precedence**

```kotlin
fun main() {
    println(1 + 2 * 3)  // Output: 7
}
```

Since `*` has **higher precedence** than `+`, it executes first.

---

## **Conclusion**

This document **covers all the essential operations in Kotlin**, including: ✔ Escape characters  
✔ Arithmetic, assignment, and logical operators  
✔ String operations  
✔ Operator precedence

It's **a great reference for mastering Kotlin operations**! Let me know if you need further clarification.