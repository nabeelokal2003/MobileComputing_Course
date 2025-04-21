### **Summary of the File: Lec4_Lec5_when_Input_Conversion.pdf**

This document contains **three Kotlin lecture topics**:

1. **Control Flow with `when` Expression**
    
2. **Type Conversion**
    
3. **User Input Handling**
    

---

## 🧠 **Lecture 5.1: Control Flow – `when` Expression**

### 🔁 **What is `when` in Kotlin?**

- Kotlin’s `when` is similar to the `switch` statement in Java/C++.
    
- It **evaluates conditions sequentially** and executes the matching branch.
    
- Can be used as:
    
    - **An expression** (returns a value)
        
    - **A statement** (performs an action)
        

---

### ✅ **Basic `when` Usage Example**

```kotlin
fun main() {
    val ch = 'A'
    when (ch) {
        'A', 'E', 'I', 'O', 'U' -> println("$ch is a Vowel")
        else -> println("$ch is a Consonant")
    }
}
```

---

### 💡 **`when` as an Expression**

```kotlin
val result = when (operator) {
    "+" -> a + b
    "-" -> a - b
    "*" -> a * b
    "/" -> a / b
    else -> "$operator is invalid"
}
```

---

### 🔄 **Combining Cases and Using Blocks**

```kotlin
when (x) {
    0, 1 -> println("x is 0 or 1")
    else -> println("otherwise")
}
```

```kotlin
when (x) {
    in 1..10 -> println("x is in range")
    !in 10..20 -> println("x is outside range")
}
```

---

## 🧠 **Type Conversion in Kotlin**

### ⚠️ **Important: Kotlin Does NOT Do Implicit Type Conversions**

```kotlin
val number1: Int = 55
val number2: Long = number1 // ❌ Error
```

### ✅ **You must use conversion functions:**

- `toInt()`, `toLong()`, `toFloat()`, `toDouble()`, `toByte()`, `toChar()`
    
- No conversions between `Boolean` and numeric types.
    

---

### 🔄 **Examples:**

```kotlin
val num = 545344
val smallNum: Byte = num.toByte()  // Truncates to 8 bits

val d = 1.7
val i = d.toInt()  // Output: 1

val c = 'B'
val ascii = c.toInt()  // Output: 66

val n = 65
val ch = n.toChar()  // Output: 'A'
```

---

### 📌 **ASCII Highlights**

|Character|Code|
|---|---|
|A-Z|65–90|
|a-z|97–122|
|Space|32|
|@|64|

---

## 🧠 **User Input in Kotlin**

### 📥 **Using `readLine()`**

- Simple way to read **String input** from the user.
    
- You can convert input using:
    

```kotlin
val x = readLine()!!.toInt()
```

### ❗ `!!` Operator

- Converts nullable `String?` from `readLine()` to non-null.
    
- **Throws exception if null** (e.g., when input is missing or redirected from file).
    

---

### ✅ **Example: Basic Input**

```kotlin
fun main() {
    print("Enter number: ")
    val num = readLine()!!.toInt()
    println("You entered: $num")
}
```

---

### 🧾 **Using Java’s Scanner for Input**

```kotlin
import java.util.Scanner

fun main() {
    val reader = Scanner(System.`in`)
    val num = reader.nextInt()
    println("You entered: $num")
}
```

- For **letters and characters**:
    

```kotlin
val ch = reader.next().single()
```

- For other types: use `nextFloat()`, `nextDouble()`, `nextLong()`, `nextBoolean()`, etc.
    

---

## ✅ Final Takeaways:

- `when` is a **powerful alternative to `if-else` and `switch`**, with **range and expression support**.
    
- Kotlin requires **explicit type conversion** to enforce type safety.
    
- For input:
    
    - Use `readLine()` for quick string-based input.
        
    - Use `Scanner` for more robust and type-specific input handling.