Here’s your **compressed, fast-review summary** of **Lecture 15 – UI Programming Part 2**, tailored for last-minute exam prep with priority on **examples and new statements** only.

---

## ✅ **Lecture 15 – UI Programming Part 2 (GJU Final Review Style)**

🎯 Focus: `CheckBox`, `RadioButton`, `ScrollView`, `Spinner` + event handling in Kotlin

---

### ✅ **CHECKBOX**

🧠 Use when the user can select **multiple options**.

#### 🔑 Key attributes:

```xml
android:checked="true"      // initially checked
android:onClick="function"  // call Kotlin function
android:clickable="false"   // disable it
android:text="Label"
```

---

### 🧪 **Example 1 – Kotlin: `setOnClickListener()`**

```kotlin
val checkBox1 = findViewById<CheckBox>(R.id.cb_single)
bt1.setOnClickListener {
    if (checkBox1.isChecked) {
        Toast.makeText(this, "Checked", Toast.LENGTH_SHORT).show()
    } else {
        Toast.makeText(this, "Unchecked", Toast.LENGTH_SHORT).show()
    }
}
```

---

### 🧪 **Example 2 – XML with `onClick="checkBoxFun"`**

```kotlin
fun checkBoxFun(view: View) {
    if (checkBox1.isChecked) {
        Toast.makeText(this, "Checked", Toast.LENGTH_SHORT).show()
    } else {
        Toast.makeText(this, "Unchecked", Toast.LENGTH_SHORT).show()
    }
}
```

---

### ✅ **RADIO BUTTON + RADIO GROUP**

🧠 Used when only **one option can be selected**.

#### 🔑 Key attributes (same as checkbox + group control):

```xml
android:checked="true"   // to preselect
android:text="Male"
```

🧠 **Always place `RadioButton` inside `RadioGroup`.**

---

### 🧪 **RadioGroup XML Example**

```xml
<RadioGroup
    android:id="@+id/radioGroup1" ... >
    <RadioButton android:id="@+id/radio1" android:text="Male" />
    <RadioButton android:id="@+id/radio2" android:text="Female" />
</RadioGroup>
```

---

### 🧪 **Kotlin: Handling Selection**

```kotlin
val radioGroup1 = findViewById<RadioGroup>(R.id.radioGroup1)
radioGroup1.setOnCheckedChangeListener { group, checkedId ->
    val radio: RadioButton = findViewById(checkedId)
    Toast.makeText(this, "Selected: ${radio.text}", Toast.LENGTH_SHORT).show()
}
```

---

### ✅ **SCROLLVIEW (Vertical)**

🧠 Use when content is **too long for screen**.

#### 🧪 **Basic Structure:**

```xml
<ScrollView
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:orientation="vertical"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">
        <!-- All your widgets go here -->
    </LinearLayout>
</ScrollView>
```
🧠 `ScrollView` accepts **only one child** — usually a `LinearLayout`.

---

### ✅ **SPINNER (Drop-down Menu)**

🧠 Use when user selects **one item from a list**, but doesn’t need to see all at once.

#### 🔑 Key attributes:

```xml
android:entries="@array/array"       // array defined in strings.xml
android:prompt="@string/text"        // title when popup opens
```

---

### 🧪 **Kotlin: Full Spinner Setup**

```kotlin
val programmingLang = arrayOf("R", "Kotlin", "Java", "Z")
val arrAda = ArrayAdapter(this, android.R.layout.simple_spinner_item, programmingLang)

val spinner = findViewById<Spinner>(R.id.spinner1)
val textView = findViewById<TextView>(R.id.textView4)

spinner.adapter = arrAda
spinner.onItemSelectedListener = object : AdapterView.OnItemSelectedListener {
    override fun onItemSelected(parent: AdapterView<*>, view: View, position: Int, id: Long) {
        textView.text = "Spinner selected: ${parent.getItemAtPosition(position)}"
    }
    override fun onNothingSelected(parent: AdapterView<*>) {}
}
```

---

## 🧠 FINAL EXAM HIGHLIGHTS:

- ✅ Know `CheckBox` vs `RadioButton` vs `Spinner`
    
- ✅ Spinner: needs adapter + onItemSelectedListener
    
- ✅ `ScrollView`: must contain **one** child layout
    
- ✅ All examples: know **how to wire XML + Kotlin**
    
- ✅ Be able to write short Kotlin methods for `onClick`, `onCheckedChangeListener`, etc.