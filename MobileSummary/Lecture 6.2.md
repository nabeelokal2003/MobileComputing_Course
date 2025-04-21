### **Summary of the File: Lec6.2_Jump Expressions & Lecture 7 Homework**

This document explains **jump expressions** in Kotlin: `break`, `continue`, and a hint about `return`. It also includes **label-based control** for nested loops and ends with **practical assignments** to apply these concepts.

---

## **1. Jump Expressions in Kotlin**

Kotlin supports 3 main jump expressions:

1. **`break`** – Terminates the nearest loop.
    
2. **`continue`** – Skips current loop iteration.
    
3. **`return`** – Exits from the current function (covered in functions later).
    

These can be used **with or without labels**.

---

## **2. `break` Statement**

### **Unlabeled Break**

- Exits the **nearest loop** immediately.
    
- Commonly used with `if`.
    

#### **Example:**

```kotlin
for (i in 1..10) {
    if (i == 5) break
    println(i)
}
```

**Output:** 1 2 3 4

---

### **Labeled Break**

- Terminates a **specific labeled loop**, helpful in **nested loops**.
    

#### **Syntax:**

```kotlin
outer@ for (...) {
    inner@ for (...) {
        if (condition) break@outer
    }
}
```

#### **Example:**

```kotlin
first@ for (i in 1..4) {
    for (j in 1..2) {
        if (i == 2) break@first
        println("i = $i; j = $j")
    }
}
```

**Output:** Stops entire loop when `i == 2`

---

## **3. `continue` Statement**

### **Unlabeled Continue**

- Skips current iteration and continues with the **next loop iteration**.
    

#### **Example:**

```kotlin
for (i in 1..5) {
    if (i == 3) continue
    println(i)
}
```

**Output:** 1 2 4 5

---

### **Continue with Conditions**

```kotlin
for (i in 1..5) {
    println("$i always printed")
    if (i > 1 && i < 5) continue
    println("$i not always printed")
}
```

---

### **Continue with Even Numbers Only**

```kotlin
for (n in 1..10) {
    if (n % 2 != 0) continue
    println(n)
}
```

**Output:** 2 4 6 8 10

---

### **Labeled Continue**

- Skips the current iteration of a **labeled loop**, giving **control in nested loops**.
    

#### **Example:**

```kotlin
outer@ for (i in 1..5) {
    for (j in 1..4) {
        if (i == 3 || j == 2) continue@outer
        println("i = $i; j = $j")
    }
}
```

**Output:** Skips whole outer iteration when condition is met.

---

## **4. `return`**

- Mentioned briefly, used to **exit from a function**.
    
- Will be explained in the **functions lecture**.
    

---

## **5. Lecture 7: Homework Assignments**

### **Assignment 1: GCD Finder**

- Input: Two integers from user.
    
- Output: Greatest Common Divisor (GCD).
    
- Example Steps:

```makefile
U = 150, V = 35 → Step1
U = 35, V = 10 → Step2
...
```

---

### **Assignment 2: Sum of Even/Odd**

- Input: 3 integers in ascending order.
    
- Output:
    
    - Sum of even numbers between 1st and 2nd.
        
    - Sum of odd numbers between 2nd and 3rd.
        

---

### **Assignment 3: Prime Numbers**

- Input: A number from user.
    
- Output: Print all **prime numbers between 1 and the input number**.
    

---

### **Assignment 4: Triangle Pattern**

```markdown
*****
****
***
**
*
```

- Use **nested for loops**.

---

### **Assignment 5: Triangle Pattern (Reversed)**

```markdown
*
**
***
****
*****
```

- Also with **nested loops**.

---

## ✅ **Conclusion**

This lecture teaches:

- **How to control loops** using `break` and `continue`
    
- **Labeled jumps** for nested loop control
    
- **Practical assignments** for deeper understanding