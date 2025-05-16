Here’s your **finals-focused, fast-recall summary** of **Lecture 18: Runtime Permission Requests in Android**, with **prioritized examples and new code explanations only** — built for rapid understanding in **GJU exam format**.

---

## ✅ Lecture 18 – Runtime Permission Requests in Android (Finals Style)

---

### 🧠 What’s Changed Since Android 6.0?

- **Before Android 6.0 (API 22 and below):**
    
    - Permissions were granted at **install time**.
        
- **Since Android 6.0 (API 23+):**
    
    - **Dangerous permissions** must be requested **at runtime**.
        
    - Examples: CAMERA, MICROPHONE, LOCATION, STORAGE, CONTACTS
        

---

## 🔐 Permission Types

|Type|How it's requested|
|---|---|
|**Install-Time**|When user installs the app (API ≤ 22)|
|**Run-Time**|Dynamically during app use (API ≥ 23)|

---

### 🧱 Step-by-Step Runtime Permission Process (🔥EXAM PRIORITY)

---

### ✅ 1. **Declare Permissions in Manifest**

```xml
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```

✅ Always **declare before** `<application>` tag!

---

### ✅ 2. **Update XML Layout with Button & ImageView**

```xml
<ImageView android:id="@+id/image_view" ... />
<Button android:id="@+id/capture_btn" android:text="Capture Image" ... />
```

---

### ✅ 3. **MainActivity.kt Logic**

#### 🔍 Check if Permission is Granted

```kotlin
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.M) {
    if (checkSelfPermission(Manifest.permission.CAMERA) == PackageManager.PERMISSION_DENIED ||
        checkSelfPermission(Manifest.permission.WRITE_EXTERNAL_STORAGE) == PackageManager.PERMISSION_DENIED) {

        // Permission not granted → request
        val permission = arrayOf(Manifest.permission.CAMERA, Manifest.permission.WRITE_EXTERNAL_STORAGE)
        requestPermissions(permission, PERMISSION_CODE)
    } else {
        openCamera()
    }
} else {
    openCamera() // no need to check on Android < 6.0
}
```

✅ `PERMISSION_CODE` is a global variable (value = 1000)

---

### ✅ 4. **Request Permission Result Handling**

```kotlin
override fun onRequestPermissionsResult(requestCode: Int, permissions: Array<out String>, grantResults: IntArray) {
    when (requestCode) {
        PERMISSION_CODE -> {
            if (grantResults.isNotEmpty() && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
                openCamera()
            } else {
                Toast.makeText(this, "Permission denied", Toast.LENGTH_SHORT).show()
            }
        }
    }
}
```

---

### ✅ 5. **Open Camera**

```kotlin
fun openCamera() {
    val values = ContentValues()
    values.put(MediaStore.Images.Media.TITLE, "New Picture")
    values.put(MediaStore.Images.Media.DESCRIPTION, "From the Camera")

    image_uri = contentResolver.insert(MediaStore.Images.Media.EXTERNAL_CONTENT_URI, values)
    val cameraIntent = Intent(MediaStore.ACTION_IMAGE_CAPTURE)
    cameraIntent.putExtra(MediaStore.EXTRA_OUTPUT, image_uri)
    startActivityForResult(cameraIntent, IMAGE_CAPTURE_CODE)
}
```

---

### ✅ 6. **Display Captured Image**

```kotlin
override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {
    if (resultCode == Activity.RESULT_OK) {
        image_view.setImageURI(image_uri)
    }
}
```

✅ `image_uri` is a global `Uri? = null` variable  
✅ `IMAGE_CAPTURE_CODE` is a global constant (value = 1000)

---

## 📊 Full List of **Dangerous Permissions** to Memorize (EXAM)

|Group|Permissions|
|---|---|
|Calendar|READ_CALENDAR, WRITE_CALENDAR|
|Camera|CAMERA|
|Contacts|READ_CONTACTS, WRITE_CONTACTS, GET_ACCOUNTS|
|Location|ACCESS_FINE_LOCATION, ACCESS_COARSE_LOCATION|
|Microphone|RECORD_AUDIO|
|Phone|READ_PHONE_STATE, CALL_PHONE|
|SMS|SEND_SMS, RECEIVE_SMS, READ_SMS|
|Storage|READ_EXTERNAL_STORAGE, WRITE_EXTERNAL_STORAGE|

---

## 🧠 Final Exam Quick Tips:

- ✅ Know when and why runtime permission is required (Android 6+)
    
- ✅ Write code to **check + request + handle** permission results
    
- ✅ Understand `Manifest.permission.X`, `PERMISSION_CODE`, and `image_uri`
    
- ✅ Be able to explain what `ContentValues` and `MediaStore` do