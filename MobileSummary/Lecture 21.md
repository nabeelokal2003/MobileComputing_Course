Here’s your **final-exam-style summary** of **Lecture 21: Animations in Android** — focused only on **new content**, **examples**, and **code usage** for fast recall under time pressure.

---

## ✅ Lecture 21 – Animations in Android (GJU Finals Cram)

---

### 🎬 **What is Animation in Android?**

- Animations = Visual changes over time (movement, fade, scale, etc.)
    
- Goal: Make UI elements **feel alive** and **interactive**
    
- Implemented via:
    
    - **XML animation files**
        
    - **Kotlin trigger using AnimationUtils**
        

---

## 🧾 **Important XML Animation Attributes (Exam-Focused)**

|Attribute|Description|
|---|---|
|`android:duration`|How long the animation runs (in ms)|
|`android:fromAlpha` / `toAlpha`|Opacity start/end (0 = transparent, 1 = opaque)|
|`android:fromYDelta` / `toYDelta`|Vertical movement delta (%) or px|
|`android:pivotX/Y`|Origin point for scaling/rotation (e.g., "50%")|
|`android:fromXScale`, `toXScale`|Start/end scale factor for width|
|`android:fromDegrees`, `toDegrees`|Start/end angle for rotation|
|`android:startOffset`|Delay before animation starts|

---

## 🗂️ **Project Structure:**

1. Modify `activity_main.xml` → Add **TextView** + 8 **Buttons**
    
2. Create a folder: `res/anim/`
    
3. Inside `anim/`, add **these XML animation files**:
    

---

## 🧪 **8 Predefined Animation XML Files**

### ✅ 1. `bounce.xml`

Bounces like a ball (multiple `translate` entries with offsets)

```xml
<translate android:fromYDelta="100%" android:toYDelta="-20%" android:duration="300"/>
```

---

### ✅ 2. `fade_in.xml`

Text appears gradually

```xml
<alpha android:fromAlpha="0.1" android:toAlpha="1.0" android:duration="1000"/>
```

---

### ✅ 3. `fade_out.xml`

Text disappears gradually

```xml
<alpha android:fromAlpha="1.0" android:toAlpha="0.1" android:duration="1000"/>
```

---

### ✅ 4. `rotate.xml`

Text rotates 360 degrees

```xml
<rotate android:fromDegrees="0" android:toDegrees="360" android:pivotX="50%" android:pivotY="50%"/>
```

---

### ✅ 5. `slide_down.xml`

Text slides from top to current position

```xml
<translate android:fromYDelta="-100%" android:toYDelta="0" />
```

---

### ✅ 6. `slide_up.xml`

Text slides from current position to top

```xml
<translate android:fromYDelta="0" android:toYDelta="-100%" />
```

---

### ✅ 7. `zoom_in.xml`

Text zooms in (gets larger)

```xml
<scale android:fromXScale="1" android:toXScale="1.5" />
```

---

### ✅ 8. `zoom_out.xml`

Text zooms out (gets smaller)

```xml
<scale android:fromXScale="1.0" android:toXScale="0.5" />
```

---

## 💻 **MainActivity.kt – How to Trigger the Animations**

🧠 Use `AnimationUtils.loadAnimation(...)` to load animation:

```kotlin
val animation = AnimationUtils.loadAnimation(this, R.anim.fade_in)
textView.startAnimation(animation)
```

---

### ✅ Examples with Button Clicks

```kotlin
bounce.setOnClickListener {
    val anim = AnimationUtils.loadAnimation(this, R.anim.bounce)
    textView.startAnimation(anim)
}

fade_in.setOnClickListener {
    textView.visibility = View.VISIBLE
    val anim = AnimationUtils.loadAnimation(this, R.anim.fade_in)
    textView.startAnimation(anim)
}

fade_out.setOnClickListener {
    val anim = AnimationUtils.loadAnimation(this, R.anim.fade_out)
    textView.startAnimation(anim)
    Handler().postDelayed({ textView.visibility = View.GONE }, 1000)
}
```

(Repeat similar logic for rotate, slide_up, slide_down, zoom_in, zoom_out)

---

## 🧠 Final Exam Priority Checklist:

- ✅ Memorize `fade_in.xml`, `rotate.xml`, `zoom_in.xml` formats
    
- ✅ Understand what each attribute does (`pivotX`, `fromAlpha`, `toYDelta`)
    
- ✅ Be able to write a click listener in Kotlin that applies animation
    
- ✅ Remember: `AnimationUtils.loadAnimation()` loads XML into action
    
- ✅ Know where to store animation XMLs → `res/anim/`