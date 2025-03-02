# Android Data Storage and UI Components

## SharedPreferences Usage
SharedPreferences is used to store small amounts of persistent data in Android applications.

### How to Use
**Initialization:**
```java
SharedPreferences prefs = getSharedPreferences("MyPrefs", MODE_PRIVATE);
```

**Saving Data:**
```java
SharedPreferences.Editor editor = prefs.edit();
editor.putString("username", "JohnDoe").apply();
```

**Retrieving Data:**
```java
String username = prefs.getString("username", "Default");
```

**Deleting Specific Data:**
```java
prefs.edit().remove("username").apply();
```

**Clearing All Data:**
```java
prefs.edit().clear().apply();
```

## Toast Messages
Toast is used to display short-lived messages to users.

**Usage:**
```java
Toast.makeText(this, "Toast Message", Toast.LENGTH_LONG).show();
```
- `Toast.LENGTH_LONG`: Displays the message for a longer duration.
- `Toast.LENGTH_SHORT`: Displays the message for a shorter duration.

## AlertDialog Usage
AlertDialog is used to present information or options to the user.

**Example:**
```java
AlertDialog.Builder alert = new AlertDialog.Builder(this);
alert.setTitle("Save");
alert.setMessage("Are you sure?");
alert.setPositiveButton("Yes", (dialog, which) -> {
    Toast.makeText(getApplicationContext(), "Saved", Toast.LENGTH_LONG).show();
});
alert.setNegativeButton("No", (dialog, which) -> {
    Toast.makeText(this, "Not Saved", Toast.LENGTH_LONG).show();
});
alert.show();
```
- **`setTitle()`**: Sets the dialog title.
- **`setMessage()`**: Defines the message displayed inside the dialog.
- **`setPositiveButton()`**: Adds a button for confirming the action.
- **`setNegativeButton()`**: Adds a button for canceling the action.
- **`show()`**: Displays the dialog.

## Understanding Context in Android
Context provides access to application resources and functionalities.

### Types of Context:
- **Activity Context:** Used within an Activity using `this` or `MainActivity.this`.
- **Application Context:** Retrieved using `getApplicationContext()`, valid throughout the app lifecycle.

**Example:**
```java
Toast.makeText(getApplicationContext(), "App Context Example", Toast.LENGTH_SHORT).show();
```

### When to Use Activity vs. Application Context?
- Use **Activity Context** when the context is tied to the UI, such as dialogs, inflating layouts, or launching new activities.
- Use **Application Context** when you need a long-lived context, such as initializing a singleton or accessing resources globally.

By understanding SharedPreferences, Toast, AlertDialog, and Context, you can efficiently manage data storage and UI interactions in Android applications.

