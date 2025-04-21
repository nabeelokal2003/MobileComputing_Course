### **Summary of the File: Lec8_Arrays.pdf**

This lecture introduces **arrays in Kotlin**—a core data structure for storing and managing collections of data. It covers declaration methods, accessing and modifying elements, built-in functions, traversal techniques, and user input. It ends with two assignments to apply your understanding.

---

## **1. What is an Array?**

- A **data structure** to store **multiple values** under one variable name.
    
- In Kotlin:
    
    - Arrays are **mutable** and have **fixed size**.
        
    - Based on the `Array` class (not primitive like in C/Java).
        
    - Can store **different types**, though best used with one.
        

---

## **2. Declaring Arrays in Kotlin**

### **Method 1: `arrayOf()`**

```kotlin
val num1 = arrayOf(1, 2, 3, 4)
val num2 = arrayOf<Int>(1, 2, 3)
```

- Can hold:
    
    - **Different types**: `arrayOf(10, "text", 10.99, 'A')`
        
    - **Only strings**: `arrayOf("ab", "cd")`
        

---

### **Method 2: `Array` Constructor**

```kotlin
val arr = Array(5) { i -> i * 1 }
```

Or with a formula:

```kotlin
val arr = Array(5) { i -> 3.14 * i * i }
```

---

### **Method 3: Factory Methods (for primitive types)**

```kotlin
val intArr = intArrayOf(1, 2, 3)
val charArr = charArrayOf('a', 'b', 'c')
```

Other variants: `byteArrayOf()`, `longArrayOf()`, `shortArrayOf()`

---

## **3. Accessing & Modifying Elements**

### **Two ways:**

1. **Bracket notation:**

```kotlin
val x = arr[0]
arr[1] = 100
```

1. **Using `get()` and `set()`:**

```kotlin
val x = arr.get(0)
arr.set(1, 3)
```


> Internally, `[]` is syntactic sugar for `get()` and `set()` methods.

---

## **4. Useful Built-In Functions**

|Function|Description|
|---|---|
|`size`|Number of elements|
|`indices`|Valid index range|
|`contains(value)`|Checks if array contains a value|
|`first()`|First element|
|`last()`|Last element|
|`indexOf(value)`|Index of a given value|

---

## **5. Array Traversal Methods**

### **Three main ways:**

```kotlin
for (i in arr.indices) println(arr[i])

for (i in 0 until arr.size) println(arr[i])

for (element in arr) println(element)
```

---

## **6. Handling Mixed-Type Arrays**

```kotlin
val arr = arrayOf(10, "text", 10.5, 'A')
println(arr[3])  // Outputs: A
arr[3] = 100
println(arr[3])  // Outputs: 100
```

---

## **7. Example: Get and Set**

```kotlin
val num = arrayOf(1, 2, 3, 4, 5)
num.set(0, 10)
println(num.get(0))  // 10
```

---

## **8. Error Example**

```kotlin
val myArray5 = intArrayOf(5, 10, 20, 12, 15)
myArray5[6] = 18  // ❌ Error: IndexOutOfBoundsException
```

Arrays in Kotlin have **fixed length** and don't allow out-of-range indexing.

---

## **9. Getting Array from User Input**

```kotlin
val arr = Array<Int>(5) { 0 }
var index = 0
while (index < arr.size) {
    println("Enter element no. $index")
    arr[index] = readLine()!!.toInt()
    index++
}
```

---

## **10. Assignments**

### **Assignment 1**

- Create array of size 5 from user input.
    
- Calculate:
    
    1. How many numbers are divisible by 3.
        
    2. Average of elements at **even indexes** (0, 2, 4).
        

---

### **Assignment 2**

- Sort an array using a manual algorithm:

```kotlin
Step 1: Set i = 0
Step 2: Set j = i + 1
Step 3: If a[i] > a[j], swap
Step 4: j++
Step 5: Repeat until array is sorted (like Bubble Sort)
```

---

## ✅ **Conclusion**

This lecture helps you:

- **Declare, modify, and access arrays**
    
- **Use built-in Kotlin array functions**
    
- **Understand array traversal**
    
- **Handle user input into arrays**
    
- **Avoid common errors (like index out of bounds)**