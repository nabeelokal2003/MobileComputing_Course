### **Summary of the File: Lec9.1_Strings.pdf**

This lecture is focused entirely on **strings in Kotlin**—how to declare, use, manipulate, and compare them, along with common string functions and regex-based operations.

---

## 🔤 **1. What is a String in Kotlin?**

- A **string is an array of characters**.
    
- In Kotlin, all strings are **instances of the `String` class**.
    
- Strings are **immutable**—you can’t change characters directly but can reassign new strings (if using `var`).
    

---

## 📝 **2. Declaring and Initializing Strings**

```kotlin
val myString = "Hey there!"
var laterInit: String
laterInit = "Howdy"
```

---

## 🔍 **3. Accessing String Characters**

- Use **indexing** with `[ ]` or `get()`:

```kotlin
val char = myString[2]     // 3rd character
val charAlt = myString.get(2)
```

- Trying to access an **invalid index** causes an error.

---

## 🔁 **4. Iterating Over Strings**

```kotlin
for (char in myString) {
    println(char)
}
```

---

## 🚫 **5. Immutability**

```kotlin
myString[0] = 'H'  // ❌ Error!
```

You **can reassign** the whole string using `var`.

---

## ✍️ **6. String Literals**

### **Two types:**

- **Escaped Strings**: Support `\n`, `\t`, `\\`, `\"`, etc.

```kotlin
val s = "Hello\nWorld"
```

- **Raw Strings**: Triple quotes `"""..."""`, useful for multiline text.

```kotlin
val s = """
    |Line 1
    |Line 2
""".trimMargin()
```

---

## 💲 **7. String Templates**

- Insert variables or expressions directly:

```kotlin
val a = 5
val s = "Value is $a"
val max = "Max is ${if (a > b) a else b}"
```

---

## 🛠️ **8. Useful String Functions & Properties**

|Function|Use Case|
|---|---|
|`.length`|Returns string length|
|`.compareTo()`|Compares two strings|
|`.get(index)`|Gets char at index (`[index]`)|
|`.plus()`|Concatenates strings (`+`)|
|`.subSequence(start, end)`|Gets substring|
|`.contains()`|Checks substring existence|
|`.replace()`|Regex/string replacement|
|`.indexOf()`|Finds index of element|
|`.first()`/`.last()`|Gets first/last element|

---

## ⚖️ **9. String Comparison**

- Use `==` or `.equals()` for **value equality**
    
- Use `===` for **reference equality** (object identity)
    

### **Examples:**

```kotlin
val a = "Kotlin"
val b = "Kotlin"
println(a == b)   // true (same content)
println(a === b)  // true (same reference in some cases)

val x = buildString { append("Bold") }
val y = buildString { append("Bold") }
println(x === y)  // false (different memory reference)
```

---

## ✂️ **10. Substrings & Search**

```kotlin
val s = "MobileApplication"
println(s.subSequence(2, 5)) // bil

val str = "GJU.EDU.JO"
println(str.contains("GJU.")) // true
```

---

## 🔄 **11. Replacing Strings with Regex**

- `.replace(pattern.toRegex(), replacement)`

### **Examples:**

```kotlin
// Remove spaces
val cleaned = "Thi s i s     hard".replace("\\s".toRegex(), "")

// Replace first character T with t
val r = "Tomorrow".replace("^T".toRegex(), "t")

// Replace last char 'w'
val r = "Tomorrow".replace("w$".toRegex(), "WW")

// Replace all letters with 9
val r = "Tomorrow".replace("[A-Za-z]".toRegex(), "9")
```

---

## 🔁 **12. Pattern-Based Replacements**

```kotlin
// Replace part of word
val r = "Tomorrow".replace("or.*".toRegex(), "oooooo")
// Custom pattern
val r = "Tomorrow".replace("o..o".toRegex(), "rrrr")
```

---

## ✅ **Conclusion**

This lecture gives you deep control over **string creation, comparison, formatting, and modification**, covering:

- String templates
    
- Raw/escaped strings
    
- Regex replacements
    
- `==` vs `.equals()` vs `===`