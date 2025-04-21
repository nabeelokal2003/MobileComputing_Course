### **Summary of the File: Lec4.2_Flow Control If.pdf**

This document **explains flow control in Kotlin**, focusing on **if expressions** and different conditional structures like `if-else`, `if-else if-else`, and **nested if expressions**. It also includes examples and an assignment for practice.

---

## **1. Flow Control in Kotlin**

- Flow control **manages program execution** based on conditions.
    
- Example: If a number is even, print "Even Number"; otherwise, print "Odd Number".
    
- Kotlin provides several control flow expressions:
    
    1. **If expression**
        
    2. **If-else expression**
        
    3. **If-else if-else expression**
        
    4. **Nested expressions**
        
    5. **When expression**
        
    6. **For loop**
        
    7. **While and do-while loops**
        

---

## **2. If Expression**

- **`if` is an expression** (not a statement like in Java), meaning it **returns a value**.
    
- Syntax:

```kotlin
if (condition) {
    // Block of code executes if condition is true
}
```

- **Curly braces `{}` are optional** if only **one statement** is inside `if`.

### **Example: Basic If Statement**

```kotlin
fun main() {
    val number = 100

    if (number % 2 == 0) {
        println("Even Number")
    }

    println("Out Of If statement")
}
```

**Output:**

```mathematica
Even Number
Out Of If statement
```

---

## **3. If-Else Expression**

- `if-else` allows executing **different blocks of code** based on a condition.
    
- Syntax:

```kotlin
if (condition) {
    // Runs if condition is true
} else {
    // Runs if condition is false
}
```

### **Example: If-Else**

```kotlin
fun main() {
    val number = -10

    if (number > 0) {
        println("Positive number")
    } else {
        println("Negative number")
    }
}
```

**Output:**

```typescript
Negative number
```

---

## **4. If as an Expression**

- Unlike Java, `if` can be **used as an expression** in Kotlin.
    
- It **returns a value** that can be assigned to a variable.
    

### **Example: If as an Expression**

```kotlin
fun main() {
    val number = -10
    val result = if (number > 0) "Positive number" else "Negative number"
    println(result)
}
```

**Output:**

```typescript
Negative number
```

- The **`else` branch is mandatory** when using `if` as an expression.

---

## **5. If-Else If-Else Ladder**

- Used for **multiple conditions**.
    
- Syntax:

```kotlin
if (condition1) {
    // Runs if condition1 is true
} else if (condition2) {
    // Runs if condition2 is true
} else {
    // Runs if none of the conditions are true
}
```

### **Example: Checking the Type of a Number**

```kotlin
fun main() {
    val num = 99

    if (num < 0) {
        println("Number is Negative")
    } else if (num > 0 && num < 10) {
        println("Single digit number")
    } else if (num >= 10 && num < 100) {
        println("Double digit number")
    } else {
        println("Number has 3 or more digits")
    }
}
```

**Output:**

```kotlin
Double digit number
```

---

## **6. Nested If Expressions**

- An **if expression inside another if expression** is called a **nested if**.
    
- Used when **checking multiple related conditions**.
    

### **Example: Nested If for Even/Odd Check**

```kotlin
fun main() {
    val num = 101

    if (num < 0) {
        println("Negative Number")
    } else {
        if (num % 2 == 0) {
            println("Even Number")
        } else {
            println("Odd Number")
        }
    }
}
```

**Output:**

```javascript
Odd Number
```

### **Example: Finding the Largest of Three Numbers**

```kotlin
fun main() {
    val n1 = 3
    val n2 = 5
    val n3 = -2

    val max = if (n1 > n2) {
        if (n1 > n3) n1 else n3
    } else {
        if (n2 > n3) n2 else n3
    }

    println("max = $max")
}
```

**Output:**

```kotlin
max = 5
```

---

## **7. Assignment: Grading System**

**Task:**

- Declare **five integer variables** representing **grades** (0-25 scale).
    
- **Convert them to a 100% scale** (multiply by 4).
    
- **Calculate and print:**
    
    - The **number of failed classes** (grade < 50%).
        
    - The **sum and average of all grades**.
        
    - **Classify the average**:
        
        - **>50 and <75** → `"Good overall"`
            
        - **>=75 and <85** → `"Very Good"`
            
        - **>=85** → `"Excellent"`
            

---

## **Conclusion**

This document provides **a clear understanding of control flow in Kotlin**, specifically: ✔ `if` expressions  
✔ `if-else` statements  
✔ `if` as an expression (returning a value)  
✔ `if-else if-else` for multiple conditions  
✔ Nested `if` for complex decision-making

It includes **plenty of examples** and an **assignment** to test your understanding! Let me know if you need any clarification.