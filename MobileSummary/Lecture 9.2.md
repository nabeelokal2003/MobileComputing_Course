### **Summary of the File: Lec9.2_Functions.pdf**

This lecture covers the **concept of functions in Kotlin**, including **how to define**, **call**, and **return values from functions**. It discusses both **standard (built-in)** and **user-defined functions**, and explores multiple styles of function body definitions.

---

## 🔧 **1. What is a Function?**

- A **function** is a reusable block of code that performs a specific task.
    
- Helps in:
    
    - **Breaking programs into smaller parts**
        
    - **Avoiding repetition**
        
    - **Improving modularity and readability**
        

---

## 🧰 **2. Types of Functions**

1. **Standard Library Functions**

- Built-in Kotlin functions like:

  ```kotlin
  print(), println(), Math.sqrt()
  ```

- Example:

```kotlin
val number = 5.5
println("Result = ${Math.sqrt(number)}")
```

1. **User-Defined Functions**
    
    - Custom functions you create for specific tasks.
        
    - Syntax:
```kotlin
fun functionName() {
    // body
}
```

---

## ▶️ **3. Calling a Function**

```kotlin
fun callMe() {
    println("Hello from function!")
}

fun main() {
    callMe()
}
```

---

## 🧪 **4. Example: Simple Function**

```kotlin
fun sayHello() {
    println("Hello")
}

fun main() {
    sayHello()
}
```

---

## 🎯 **5. Function with Arguments and Return Type**

### **Syntax:**

```kotlin
fun functionName(param1: Type, param2: Type): ReturnType {
    // logic
    return value
}
```

### **Example: Add Two Numbers**

```kotlin
fun addNumbers(n1: Double, n2: Double): Int {
    val sum = n1 + n2
    return sum.toInt()
}

fun main() {
    val result = addNumbers(12.2, 3.4)
    println("Result = $result")  // Output: 15
}
```

---

## 🧾 **6. Function Parameters: Key Notes**

- **Actual arguments**: Passed during function call.
    
- **Formal parameters**: Defined in the function.
    
- Their **data types must match**.
    

---

## 📝 **7. Returning Strings – 3 Function Body Options**

### ✅ Option 1 (Block Body):

```kotlin
fun getName(first: String, last: String): String {
    val name = "$first $last"
    return name
}
```

### ✅ Option 2 (Shorter Block):

```kotlin
fun getName(first: String, last: String): String {
    return "$first $last"
}
```

### ✅ Option 3 (Expression Body):

```kotlin
fun getName(first: String, last: String): String = "$first $last"
```

---

## 🧮 **8. Function That Does Not Return a Value**

- Return type is `Unit` (equivalent to `void`).
    
- It's optional to write `: Unit`.
    

```kotlin
fun sum() {
    val num1 = 5
    val num2 = 6
    println("sum = ${num1 + num2}")
}

fun main() {
    sum()
    println("code after sum")
}
```

**Output:**

```bash
sum = 11  
code after sum
```

---

## ✅ **Conclusion**

By the end of this lecture, you understand how to:

- Use built-in Kotlin functions.
    
- Define and call your own functions.
    
- Work with parameters and return types.
    
- Write functions in multiple styles (block, expression).
    
- Make your code modular, reusable, and more maintainable.