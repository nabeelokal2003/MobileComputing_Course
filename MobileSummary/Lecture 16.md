Here’s your **exam-cram style summary** of **Lecture 16 – UI Programming Part 3**, focused on **ListView**, Kotlin interaction, and **new keywords and examples** only.

---

## ✅ **Lecture 16 – UI Programming Part 3 (Final Exam Focus)**

### 📋 **Main Focus: ListView in Kotlin (Legacy)**

- Displays a **vertical scrollable list** of items
    
- Good for showing simple lists like cities, countries, names, etc.
    

---

### 🔸 **Basic ListView XML Setup**

```xml
<ListView
    android:id="@+id/listView1"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
```

🧠 `android:entries="@array/array"` → links a predefined array from `strings.xml`

---

### 🧪 **New Kotlin Code: Simple ListView with Cities**

```kotlin
val cities = arrayOf("Melbourne", "Vienna", "Vancouver", "Toronto", "Calgary", "Adelaide", ...)
val myListView = findViewById<ListView>(R.id.listView1)
val arrayAdapter = ArrayAdapter(this, android.R.layout.simple_list_item_1, cities)
myListView.adapter = arrayAdapter
```

✅ `ArrayAdapter`: connects your data array with the ListView layout  
✅ `simple_list_item_1`: default single-line list item layout

---

### 🧠 **Must Place Code in:**

```kotlin
override fun onCreate(...) {
    // all adapter and findViewById code goes here
}
```

---

### 🖱️ **Add Item Click Handling**

🧪 **Example: onItemClickListener**

```kotlin
myListView.onItemClickListener = object : AdapterView.OnItemClickListener {
    override fun onItemClick(parent: AdapterView<*>, view: View, position: Int, id: Long) {
        val itemValue = myListView.getItemAtPosition(position) as String
        Toast.makeText(applicationContext, "Position: $position\nItem: $itemValue", Toast.LENGTH_LONG).show()
    }
}
```

🧠 You must cast the item value from `Any` to `String` using `as String`.

---

## 🧲 **Other List Adapters (know these!)**

|Adapter Type|Use Case|
|---|---|
|`ArrayAdapter`|Simple lists like strings|
|`CursorAdapter`|Data from database query|

Syntax:

```kotlin
ArrayAdapter(activity, layout, array)
```

---

## 🎯 **ListView Event Types (Exam-Important)**

|Event Type|Triggered When...|
|---|---|
|`setOnItemClickListener`|Item is clicked|
|`setOnItemLongClickListener`|Item is clicked and held|
|`setOnItemSelectedListener`|Item is selected (focus)|
|`onTouch`, `onScroll`, `onHover`|Other UI interactions|

---

### ✅ Final Exam Priority Checklist:

- Know how to build ListView using:
    
    - XML with `@+id` and Kotlin with `findViewById`
        
    - `ArrayAdapter` syntax
        
- Understand the **use of `onItemClickListener`** and how to extract clicked item
    
- Recognize other event listeners like `onItemSelectedListener`
    
- Know the role of adapters in **displaying dynamic data** from arrays or DB