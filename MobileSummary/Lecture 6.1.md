### **Summary of the File: Lec6.1_Flow Control Loops.pdf**

This lecture is all about **loops in Kotlin**: how to repeat code efficiently using different types of loops—`for`, `while`, and `do...while`. It includes **syntax, examples, user input integration**, and **extra practice questions**.

---

## **1. What Are Loops?**

Loops help **repeat a block of code** until a condition becomes false. Kotlin supports three main loop types:

1. `for` loop
    
2. `while` loop
    
3. `do...while` loop
    

---

## **2. For Loop in Kotlin**

### **Key Points:**

- Iterates through **ranges**, **collections**, **arrays**, and **strings**.
    
- Kotlin does **not** support Java’s C-style `for (int i = 0; i < 10; i++)` loop.
    

### **Basic Syntax:**

```kotlin
for (i in 1..5) {
    println(i)
}
```

---

### **Useful Variations:**

- **Reverse order**: `for (i in 4 downTo 1)`
    
- **Custom steps**: `for (i in 1..8 step 2)`
    
- **Excluding last number**: `for (i in 1 until 10)` excludes 10
    
- **Loop through string**:
    
    - `for (char in text)` or
        
    - `for (i in text.indices) println(text[i])`
        

### **With `if` inside loop:**

```kotlin
for (char in myString) {
    if (char == 'i') count++
}
```

### **With User Input:**

```kotlin
val start = readLine()!!.toInt()
val end = readLine()!!.toInt()
for (i in start..end) println(i)
```

---

## **3. While Loop in Kotlin**

### **Syntax:**

```kotlin
while (condition) {
    // code block
}
```

### **Behavior:**

- Executes the block **as long as the condition is true**.
    

### **Example:**

```kotlin
var i = 1
while (i <= 5) {
    println("Line $i")
    i++
}
```

---

## **4. Do...While Loop in Kotlin**

### **Key Difference:**

- Executes **at least once**, even if the condition is false.
    

### **Syntax:**

```kotlin
do {
    // code block
} while (condition)
```

### **Example:**

```kotlin
var sum = 0
do {
    val input = readLine()!!
    sum += input.toInt()
} while (input != "0")
```

---

## **5. Infinite Loops**

**Bad practice unless needed intentionally**:

```kotlin
while (true) { ... }  // Runs forever
```

or

```kotlin
do {
    ...
} while (true)
```

### **Examples of common mistakes:**

```kotlin
var num = 10
while (num >= 5) {
    println(num)
    num++ // Condition stays true forever
}
```

---

## **6. Nested Loops**

Useful for patterns and tables:

```kotlin
for (i in 1..3) {
    for (j in 1..4) {
        println("$i $j")
    }
}
```

---

## **7. Extra Practice Questions**

### **Example: Print digits in reverse**

```kotlin
var number = readLine()!!.toInt()
while (number != 0) {
    val digit = number % 10
    print(digit)
    number /= 10
}
```

### **Example: Print pattern**

```kotlin
for (row in 1..5) {
    for (col in 1..5) {
        if (col == 3) print("*") else print("#")
    }
    println()
}
```

**Output:**

```shell
##*##
##*##
##*##
##*##
##*##
```

---

## **Conclusion**

This lecture gives a solid foundation in:

- **Loop structures in Kotlin**
    
- Using loops with **input and conditions**
    
- Understanding **loop behavior**, including **infinite loops**
    
- Creating **patterns and nested loops**