Here’s your **compressed, fast-study summary** of **Lecture 14: UI Programming – Part 1**, focused on **what’s new** with **exam-priority examples** for a CS student preparing last-minute for finals:

---

## ✅ **Lecture 14 – UI Programming Part 1 (Android/Kotlin)**

🎯 Focus: Buttons, EditText, ImageButton, ImageView, TextView + Adding Actions

---

### 🧱 **Modifying the UI**

- UI is stored in `res/layout/activity_main.xml`.
    
- Load the layout in **Design view** or XML.
    
- You can either:
    
    - **Write XML manually** OR
        
    - Use **drag-and-drop from the Palette**  
        ✅ Always define **horizontal & vertical constraints**!
        

---

### 🔄 **Switch Orientation**

- Portrait ↔ Landscape: Use the icon left of the device name in the preview toolbar.
    

---

## 🔘 **New UI Widgets & Usage**

### ✅ **1. Button**

- Standard clickable button.
    
- Can be styled via XML or Attributes tab.
    

---

### ✅ **2. ImageButton**

- Like a Button, but shows an image.
    
- Subclass of `ImageView`.
    

🧠 **Example: How to import image**

1. Right-click `res/drawable` → Show in Explorer
    
2. Drag your image into `drawable`
    
3. In Android Studio, **drag ImageButton** from the Palette → Choose your image from **Project > drawable**
    

---

### ✅ **3. TextView**

- Shows static, **non-editable text** (e.g., results, labels)
    

---

### ✅ **4. EditText (Many Types!)**

Used for **user input** — exam may ask you to **match type with keyboard behavior**:

|Type|Input Behavior|
|---|---|
|Plain Text|Default keyboard|
|Password|Masked input|
|Password (Num)|Numeric + masked|
|E-mail|Keyboard with `@`|
|Phone|Phone pad layout|
|Postal Address|Default text keyboard|
|Multiline Text|Adds Enter for new lines|
|Time|Numeric + `:`|
|Date|Numeric + `/`|
|Number|Only digits|
|Number (Signed)|Allows `+` or `-`|
|Number (Decimal)|Allows decimal point|

---

### ✅ **5. ImageView**

- Displays static images.
    

🧠 Import same as ImageButton:

- Drag image into `drawable` → Drag ImageView from Palette → Assign the image.
    

---

## 🧠 **Adding Action to UI (Very Important)**

### ✅ **Example Goal:**

Take a radius from EditText → On button click → Show area in TextView

---

### 🧪 **Method 1: Use `onClick` from XML**

```kotlin
fun areaOfCircle(view: View) {
    val radius = Radius.text.toString().toFloat()
    val area = radius * radius * 3.14
    textView.text = area.toString()
}
```

- Must match function name with XML `onClick` attribute
    
- Android auto-imports `import android.view.View` if needed
    

---

### 🧪 **Method 2: Use `setOnClickListener` in Kotlin**

```kotlin
override fun onCreate(...) {
    ...
    val bt1 = findViewById<Button>(R.id.BT1)
    val tv = findViewById<TextView>(R.id.textView)
    val et = findViewById<EditText>(R.id.Radius)

    bt1.setOnClickListener {
        val radius = et.text.toString().toFloat()
        val area = radius * radius * 3.14
        tv.text = area.toString()
    }
}
```

✅ This is cleaner and used **more often in real-world apps**  
✅ `ALT + ENTER` imports missing widgets automatically

---

### 🍞 **Toast – Show Temporary Message**

```kotlin
Toast.makeText(this, "Success", Toast.LENGTH_SHORT).show()
Toast.makeText(this, "Longer Success", Toast.LENGTH_LONG).show()
```

🧠 Toast = Small popup, not clickable, disappears after a short time.

---

### 🎲 **Random Number Generator**

```kotlin
var i = Random.nextInt(10)
```

✅ Randomly generates number **from 0 to 9**

---

## 📌 Final Exam Checklist:

- Know difference between:
    
    - `TextView` vs `EditText`
        
    - `ImageView` vs `ImageButton`
        
    - `onClick` vs `setOnClickListener`
        
- Understand all `EditText` input types
    
- Be able to **write Kotlin code to take input, process it, and show output**
    
- Know how to **import and assign images** in UI
    
- Expect MCQs or small code questions on **Toast** and `Random.nextInt()`