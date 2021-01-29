# Basics

# Tell all the Android application components

- Application components are the essential building blocks of an Android application.
-	These components are loosely coupled by the application manifest file. 
-	AndroidManifest.xml describes each component of the application and how they interact.
-	There are four different types of app components:
  - Activities
  - Services
  - Broadcast receivers
  - Content providers

# Intents and Broadcasting

# What is Intent?

- Intents are messages that can be used to pass information to the various components of android. 
- It is used to launch an activity, display a web page, send SMS, send email, etc. 
- There are two types of intents in android:
  - Implicit Intent
  - Explicit Intent
  
# What is Implicit Intent?

- By using the Implicit Intents you can communicate between various applications present in the mobile device 
  (i.e.) Implicit intent is when you call system default intent like send email, send SMS, dial number. 
-	For example, you can access the current location by accessing the location data from other application also 
  (i.e.) if one application A is detecting the current location of the user then you can use the data of the user 
  (i.e.) the current location by communicating with application A.
  
# What is Explicit Intent?

- If you want communication between the components of your application only then you can use the Explicit Intents.
- Explicit Intents are used to communicate with a particular component of the same application.
- For example, if you want to launch an Activity by clicking some button on the present Activity.
  
# What is	Pending Intent? 
- If you want someone to perform any Intent operation at future point of time on behalf of you, then we will use Pending Intent.
-	A PendingIntent is generally used in cases were an AlarmManager needs to be executed or for Notification. 
- A PendingIntent provides a means for applications to work, even after their process exits.

# What is Intent Filter? 
- Android OS uses filters to pinpoint the set of Activities, Services, and Broadcast receivers that can handle the Intent with help of specified set of action, categories, data scheme associated with an Intent. 
-	You will use <intent-filter> element in the manifest file to list down actions, categories and data types associated with any activity, service, or broadcast receiver.
  
# What is Sticky Intent?
- These are the Intents which sticks with Android system for future broadcast listener.
- Sticky Intents allows communication between a function and a service. 
- For example if BATTERY_LOW event occurs then that Intent will stick with Android so that any future requests for BATTERY_LOW, will return the Intent.
