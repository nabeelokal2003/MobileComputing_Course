Here’s your **fast-study final exam summary** of **Lecture 17: Intents in Android (GJU Style)** — designed for a CS student under time pressure with focus on **new statements and examples only**.

---

## ✅ **Lecture 17 – Intents in Android (Final Exam Style)**

---

### 🧠 What are Intents?

- **Intent** = messaging object used to **launch activities** or **perform actions**
    
- It can:
    
    - Start a new activity
        
    - Pass data between activities
        
    - Launch other apps (e.g., browser)
        

---

## 🧭 **Two Types of Intents**

|Type|Description|Example Use Case|
|---|---|---|
|**Explicit**|Target a specific activity/class|Move from Login → Dashboard|
|**Implicit**|Ask Android system to find a handler for the action|Open a website in browser|

---

## ✍️ **How to Add a New Activity**

From Android Studio:  
**Right-click → New → Activity → Empty Activity**

🔧 This creates:

1. A new XML layout
    
2. A new Kotlin class file
    
3. Registers the activity inside `AndroidManifest.xml` (🚨 mandatory)
    

🧪 **Manifest example (Exam priority)**:

```xml
<activity android:name=".SecondActivity" />
```

---

### ✅ **EXPLICIT INTENT (WITH EXAMPLES)**

#### 🧪 MainActivity.kt:

```kotlin
val intent = Intent(this, SecondActivity::class.java)
intent.putExtra("course_name", "Mobile Application Development")
intent.putExtra("your_name", editText1.text.toString())
startActivity(intent)
```

✅ `putExtra()` passes data to the next activity  
✅ `startActivity()` launches it

---

#### 🧪 SecondActivity.kt:

```kotlin
val intent = intent
val courseName = intent.getStringExtra("course_name")
val yourName = intent.getStringExtra("your_name")

txtView2.text = "Your name is: $yourName"
txtView3.text = "Course name is: $courseName"
```

✅ Use `getStringExtra()` to **receive passed values**

---

### 🧪 Navigating Back or Forward:

```kotlin
// Back to MainActivity
val intent = Intent(this, MainActivity::class.java)
startActivity(intent)

// Forward to ThirdActivity
val intent = Intent(this, ThirdActivity::class.java)
startActivity(intent)
```

---

### ✅ **ThirdActivity.kt: Open a Website (Using IMPLICIT Intent)**

```kotlin
val i = Intent(Intent.ACTION_VIEW, Uri.parse("https://www.vogella.com/"))
startActivity(i)
```

✅ No class name provided = **implicit**  
✅ Android chooses the browser app to handle the action

---

## 📝 EXAM KEYWORDS TO KNOW:

- **Intent**: triggers navigation or system events
    
- **Explicit**: target is known (class is specified)
    
- **Implicit**: action is declared, system finds the handler
    
- `putExtra()` and `getStringExtra()`
    
- `startActivity()`
    
- `AndroidManifest.xml` — must register activities
    
- Know the difference between **data transfer** and **UI navigation**
    

---

### 📌 Final Exam Must-Know Checklist:

- ✅ Code to switch between activities (explicit intent)
    
- ✅ Code to open browser (implicit intent)
    
- ✅ How to pass and receive data using `putExtra()` and `getStringExtra()`
    
- ✅ Purpose of AndroidManifest.xml
    
- ✅ UI flow between MainActivity, SecondActivity, and ThirdActivity