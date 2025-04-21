### **Summary of the File: Lec10_Classes_Objects_Inheritance.pdf**

This lecture introduces **Object-Oriented Programming (OOP) in Kotlin**, covering **classes**, **objects**, **inheritance**, **access modifiers**, **function overriding**, and **how to use `super`**.

---

## 🧱 **1. What Is a Class in Kotlin?**

- A **class** is a blueprint for creating objects.
    
- Classes include:
    
    - **Properties** (variables inside a class)
        
    - **Methods** (functions inside a class)
        

### 🔨 Syntax:

```kotlin
class MyClass {
    var number: Int = 5
    fun calculateSquare(): Int {
        return number * number
    }
}
```

---

## 🧍 **2. Creating Objects**

- You use the class to create instances (objects):

```kotlin
val obj = MyClass()
println(obj.calculateSquare())
```

---

## 💡 **3. Kotlin Class Example: Lamp**

```kotlin
class Lamp {
   var isOn: Boolean = false
   fun turnOn() { isOn = true }
   fun turnOff() { isOn = false }
   fun displayLightStatus(name: String) {
       if (isOn) println("$name lamp is on.") 
       else println("$name lamp is off.")
    }
}
```

---

## 🔐 **4. Access Modifiers**

|Modifier|Accessibility|
|---|---|
|`private`|Inside the class only|
|`protected`|Inside the class and its subclasses|
|`public`|Everywhere (default if not specified)|

---

## 🧬 **5. Inheritance in Kotlin**

### ✅ Benefits:

- **Avoid code duplication**
    
- **Reuse common behaviors**
    
- Supports “**is-a**” relationship  
    (e.g., `Footballer` is a `Person`)
    

### 🧱 Syntax:

```kotlin
open class Person { ... }       // Base class
class Footballer : Person() {   // Derived class
    fun play() { println("Playing football") }
}
```

---

## 🧪 **Example: Inheritance**

```kotlin
open class Person {
    var name = ""
    var age = 0
    fun printInfo() {
        println("My name is $name, age $age")
    }
}

class MathTeacher : Person() {
    fun teachMaths() = println("Teaching math")
}
```

---

## 🌀 **6. Overriding Functions and Properties**

### ✅ Overriding Functions:

```kotlin
open class Person {
    open fun displayAge(age: Int) = println("Age is $age")
}

class Girl : Person() {
    override fun displayAge(age: Int) = println("Fake age is ${age - 5}")
}
```

### ✅ Overriding Properties:

```kotlin
open class Animal {
    open var color = "White"
}

class Dog : Animal() {
    override var color = "Black"
}
```

---

## 🧲 **7. Using `super` Keyword**

Used to **access base class members** from the derived class.

```kotlin
open class Person {
    open fun displayAge(age: Int) = println("Actual age is $age")
}

class Girl : Person() {
    override fun displayAge(age: Int) {
        super.displayAge(age)
        println("Fake age is ${age - 5}")
    }
}
```

---

## 🧠 **8. Real-World Inheritance Design**

Example:

- **Base Class:** `Person` → methods: `walk()`, `talk()`, `eat()`
    
- **Derived Classes:**
    
    - `MathTeacher` → `teachMaths()`
        
    - `Footballer` → `playFootball()`
        
    - `Businessman` → `runBusiness()`
        

Use inheritance when the child "is a" type of the parent.

---

## ✅ **Conclusion**

This lecture provides a foundation for OOP in Kotlin. It teaches how to:

- Define and instantiate **classes and objects**
    
- Use **access modifiers** for encapsulation
    
- Apply **inheritance** for code reuse
    
- **Override** methods and properties
    
- Use `super` to access base class functionality