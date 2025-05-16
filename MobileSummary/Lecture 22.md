Here’s your **finals-focused Kotlin summary** of **Lecture 22: Notifications in Android**, prioritized for **GJU-style exams**, with all new examples and steps explained clearly and quickly.

---

## ✅ Lecture 22 – Notifications in Android (Finals Edition)

---

### 📣 What is a Notification?

- A short message that shows outside the app.
    
- Works even when the app isn’t running.
    
- Includes: **Icon**, **Title**, and **Text**.
    

---

## 📲 Step-by-Step to Send Notifications

---

### ✅ Step 1: Create a New Project

- Language: Kotlin
    
- Empty Activity
    
- Any minimum SDK (but must support API 26+ for notifications)

---

### ✅ Step 2: Modify `activity_main.xml`

Add a Button to trigger notification:

```xml
<Button
    android:id="@+id/btn_1"
    android:text="Send Notification"
    ... />
```

---

### ✅ Step 3: Create a Second Activity

🧠 This will open **when the user clicks** the notification.

#### `AfterNotification.kt`

```kotlin
class AfterNotification : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_after_notification)
    }
}
```

#### `activity_after_notification.xml`

```xml
<TextView android:text="Activity After Notifications" ... />
```

---

## 🚨 Step 4: Create a Notification Channel (API 26+ Required)

```kotlin
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
    val channelId = "com.example.notifications"
    val description = "Test notification"

    val notificationChannel = NotificationChannel(
        channelId,
        description,
        NotificationManager.IMPORTANCE_DEFAULT
    )

    notificationChannel.enableLights(true)
    notificationChannel.lightColor = Color.GREEN
    notificationChannel.enableVibration(false)

    val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
    notificationManager.createNotificationChannel(notificationChannel)
}
```

🧠 **Why this matters:**

- Android 8+ requires channels
    
- Channel ID is mandatory for `Notification.Builder`
    

---

## ⏳ Step 5: Create a PendingIntent

```kotlin
val intent = Intent(this, AfterNotification::class.java)
val pendingIntent = PendingIntent.getActivity(
    this,
    0,
    intent,
    PendingIntent.FLAG_UPDATE_CURRENT
)
```

🧠 `PendingIntent` = Defines what happens **when notification is clicked**

---

## 🔧 Step 6: Build the Notification

```kotlin
val builder = Notification.Builder(this, channelId)
    .setSmallIcon(android.R.drawable.ic_dialog_info)
    .setContentTitle("Example Notification")
    .setContentText("This is an example notification.")
    .setContentIntent(pendingIntent)
```

🧠 Must include:

- `setSmallIcon()` → required
    
- `setContentTitle()` & `setContentText()` → message info
    
- `setContentIntent()` → user redirection
    

---

## 📤 Step 7: Send Notification Using NotificationManager

```kotlin
val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
notificationManager.notify(1001, builder.build())
```

🧠 `notify(ID, notification)` actually **displays** the notification

---

### ✅ Summary Flow:

1. Declare permissions & layouts
    
2. Create second activity
    
3. Set up notification channel (API ≥ 26)
    
4. Build pending intent
    
5. Use `Notification.Builder(...)`
    
6. Send with `notify(...)`
    

---

## 🧠 Final Exam Checklist:

- ✅ Know how to set up notification channel (`NotificationChannel`)
    
- ✅ Understand `PendingIntent` purpose and usage
    
- ✅ Code to build and send notification
    
- ✅ Difference between `NotificationManager` and `Notification.Builder`
    
- ✅ Click event opens a new activity via intent