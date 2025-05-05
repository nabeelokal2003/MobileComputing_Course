Here’s your **compressed, final-exam-focused summary** of **Lecture 13: XML in Android Studio**, tailored for fast studying with **prioritized examples** and **new statement explanations only**:

---

## ✅ **XML in Android – Exam-Focused Summary (Lec13)**

---

### 🔸 **What is XML and Why It Matters**

- XML = **Extensible Markup Language**
    
- It **describes UI elements**, not behavior (that’s Kotlin’s job).
    
- Every Kotlin activity (e.g. `MainActivity.kt`) is paired with an XML layout (e.g. `activity_main.xml`).
    

🧠 **Main point:** `setContentView(R.layout.activity_main)` links your XML to Kotlin code.

---

### 📂 **Basic XML Layout Structure**

Each XML file starts like this:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ConstraintLayout ...>
    <!-- UI elements go here -->
</ConstraintLayout>
```

🟩 **New Example Element:**

```xml
android:layout_width="match_parent"
android:layout_height="match_parent"
```

✅ `match_parent`: fill entire space  
✅ `wrap_content`: size to fit content  
✅ Specific size: `"35dp"`, `"20sp"`, etc.

---

### 📏 **Measurements Used in Layouts**

| Unit               | Meaning                                  |
| ------------------ | ---------------------------------------- |
| `dp`               | Density-independent pixels (recommended) |
| `sp`               | Scaled pixels (for fonts)                |
| `px`               | Actual pixels (not preferred)            |
| `in` / `mm` / `pt` | Physical units (less common)             |

---

### 🎯 **Key Example: Simple Layout**

```xml
<ConstraintLayout ...>

    <Button
        android:text="Click me !!"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/button"
        android:layout_marginBottom="40dp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
    />

</ConstraintLayout>
```

🧠 **What’s new here:**

- `app:layout_constraint...`: connects element to parent/container
    
- `android:layout_marginBottom`: space _outside_ element (not inside like padding)

---

➕ **Add Another Widget: TextView**

```xml
<TextView
    android:text="Hello World from Kotlin"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:id="@+id/textView"
    android:layout_marginBottom="72dp"
    app:layout_constraintBottom_toTopOf="@+id/button"
    app:layout_constraintLeft_toLeftOf="parent"
    app:layout_constraintRight_toRightOf="parent"
/>
```

🧠 **New Concepts Introduced:**

- `layout_marginBottom="72dp"`: space between `TextView` and the button below it
    
- Constraints control position relative to **parent or other views**

---

### 🎨 **Styling Elements (Button/TextView)**

Use attributes to **customize look**:

🟦 **Example:**

```xml
<Button
    android:background="#EEFF00"
    android:textSize="35dp"
    android:fontFamily="casual"
    android:textStyle="bold"
    android:textColor="#9C27B0"
/>
```

📌 New attributes explained:

- `android:background`: color (hex or resource)
    
- `android:textSize`: font size
    
- `android:fontFamily`: font face (e.g. casual)
    
- `android:textStyle`: bold, italic, or combination
    
- `android:textColor`: sets font color

---

### 🌈 **Color Management with XML**

Define colors once in `res/values/colors.xml`:

```xml
<color name="colorPrimary">#008577</color>
```

Then reference it:

```xml
android:background="@color/colorPrimary"
```

🧠 This keeps UI consistent and easier to change.

---

### 🧭 **Where Else Is XML Used?**

- `colors.xml` — for theme & color variables
    
- `AndroidManifest.xml` — defines app name, icon, launch activity, permissions

---

## 🧠 FINAL EXAM QUICK TIPS:

- Understand `ConstraintLayout` & its **constraint attributes**
    
- Know difference between **margin** (outside) and **padding** (inside)
    
- Memorize `match_parent` vs `wrap_content`
    
- Know how to link XML to Kotlin using `setContentView(...)`
    
- Practice reading and writing XML with **ID, text, size, and constraints**