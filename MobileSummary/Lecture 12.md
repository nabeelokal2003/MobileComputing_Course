Here's your **exam-focused, fast-learning summary** of **Lecture 12: Introduction to Android Studio** — optimized for a **CS student studying under time pressure** before the final:

---

## ✅ **Android Studio – Final Exam Summary (GJU Style)**

### 📌 What is Android Studio?

- Official IDE by Google for Android app development.
    
- Includes code editor, debugger, emulator, and Gradle build tools.
    
- Replaced Eclipse since v1.0 (Nov 2014); now based on **IntelliJ IDEA**.
    
- Current version: **2023.2.1**
    

---

### 🧱 **Creating a New Android Project (Step-by-step)**

1. Open Android Studio → **Start a new project**
    
2. Choose **Empty Activity**
    
3. Fill in:
    
    - Name: `My First App`
        
    - Package: `com.example.myfirstapp`
        
    - Language: Kotlin
        
    - Use `androidx.*` artifacts (check this box)
        
4. Click **Finish**
    

---

### 📂 **Project Structure (important for the exam)**

- **Project filters:**
    
    - `Project` view: All modules/files.
        
    - `Android` view: Organized by app type.
        

#### 🔑 Top-level folders:

| Folder        | Content                              |
| ------------- | ------------------------------------ |
| **Manifests** | `AndroidManifest.xml` file           |
| **Java**      | Kotlin/Java source code              |
| **Res**       | Resources (images, layouts, strings) |
| **Gradle**    | Build scripts (e.g., build.gradle)   |

---

### 🧾 **AndroidManifest.xml**

- Required file for every app.
    
- Declares:
    
    - `application`: general app settings
        
    - `activity`: app screens
        
    - `uses-permission`: e.g. `INTERNET`
        
    - `service`: for background tasks
        
    - `receiver`: for system broadcasts
        

📍**Must-have tags:** `<manifest>` and `<application>`

---

### ⚙️ **Gradle (Build System)**

- Converts your code → APK (installable app).
    
- Two `build.gradle` files:
    
    - **Project-level** (general settings)
        
    - **Module-level** (most edited)
        

💡 Module-level config:

```kotlin
compileSdkVersion 28
minSdkVersion 14
targetSdkVersion 28
```

📌 You also define dependencies here (e.g., Kotlin stdlib, AndroidX)

---

### 📱 **Running Your App**

#### 🔌 **On a Physical Device:**

1. Enable **USB Debugging** (tap Build Number 7 times in settings)
    
2. Connect device via USB
    
3. Select device in **Run** menu → Click **Run ▶**
    

#### 💻 **On an Emulator (AVD):**

1. Create AVD via **AVD Manager** (Tools > AVD Manager)
    
2. Select device profile + system image
    
3. Click **Run ▶**

---

### **AVD (Android Virtual Device) Quick Guide**

- Simulates real devices: phone, tablet, Wear OS, etc.
    
- AVD includes:
    
    - Hardware profile
        
    - System image (API version)
        
    - Storage, skin, device behavior

---

### 🛠️ **Emulator Toolbar Functions (know these!)**

|Button|Description|
|---|---|
|**Power**|Simulates phone’s power button|
|**Volume**|Control sound|
|**Rotate**|Switch portrait/landscape|
|**Screenshot**|Takes screen capture|
|**Zoom**|Toggles zoom mode|
|**Back**|Android’s back button|
|**Home**|Go to home screen|
|**Overview**|Show recent apps|
|**Fold Device**|Only on foldable AVDs|
|**Extended Controls**|Simulate GPS, battery, etc.|

---

## 🧠 What to Focus On for the Final Exam:

- What each folder does (`res`, `java`, `manifest`)
    
- `AndroidManifest.xml` structure and usage
    
- Steps to create + run an app
    
- Gradle purpose and structure
    
- AVD vs. physical device
    
- Emulator toolbar buttons