# Basics

## Tell all the Android application components

- Application components are the essential building blocks of an Android application.
-	These components are loosely coupled by the application manifest file. 
-	AndroidManifest.xml describes each component of the application and how they interact.
-	There are four different types of app components:
    - Activities
    - Services
    - Broadcast receivers
    - Content providers
    
## Activity

- An activity represents a single screen with a user interface just like window or Containers.
- Android activity is the subclass of ContextThemeWrapper class.

## Activity Lifecycle

- onCreate -> Called when activity is first created.  
- onStart -> Called when activity is becoming visible to the user.
- onResume -> Called when activity will start interacting with the user.
- onPause -> Called when activity is not visible to the user.
- onStop -> Called when activity is no longer visible to the user.
- onRestart -> Called after your activity is stopped, prior to start.
- onDestroy -> Called before the activity is destroyed.

## What is Manifest.xml?

- AndroidManifest.xml describes each component of the application and how they interact.
- The AndroidManifest.xml file contains information of your package, including components of the application such as activities, services, broadcast receivers, content           providers etc.

## What is the project structure of an Android Application?

- It consists of AndroidManifest.xml, Java, drawable, layout, mipmap, colors.xml, strings.xml, styles.xml and build.gradle(Module: app).

## Content Provider

- A content provider component supplies data from one application to others on request and such requests are handled by the methods of the ContentResolver class. 
- A content provider can use different ways to store its data and the data can be stored in a database, in files, or even over a network.

## Broadcast Receiver

- Broadcast Receivers simply respond to broadcast messages from other applications or from the system itself. 
- These messages are sometime called events or intents.
- When overriding the onReceive() method where each message is received as an Intent object parameter.
- There are two ways to register a BroadcastReceiver.
- __Static Broadcast Receivers__ These types of Receivers are declared in the manifest file and works even if the app is closed.
- __Dynamic Broadcast Receivers__ These types of receivers work only if the app is active or minimized.

## Types of Broadcasts

There are two types of broadcasts received by receivers and they are:

__Normal Broadcasts__

- These are asynchronous broadcasts.
- Receivers of this type of broadcasts may run in any order, sometimes altogether.
- This is efficient.
- Receivers cannot use the result.
- They cannot abort the included APIs.
- These broadcasts are sent with Context.sendBroadcast

__Ordered Broadcasts__

- These are synchronous broadcasts.
- One broadcast is delivered to one receiver at a time.
- Receivers can use the result. 
- In fact as each receiver executes, result is passed to next receiver.
- Receiver can abort the broadcast and hence no broadcast is received by other receivers.
- The order of receivers is managed and controlled by the attribute android:priority in corresponding intent-filter.
- If receivers will have same priority then they may run in any order.

## Context

- It is the context of the current state of the application.
- It can be used to get information regarding the activity and application.
- It can be used to get access to resources, databases, and shared preferences, and etc.
- Both the Activity and Application classes extend the Context class.
- Types of Context -> Application Context, Activity Context

## Application Context

- This context is tied to the lifecycle of an application. 
- The application context can be used where you need a context whose lifecycle is separate from the current context or when you are passing a context beyond the scope of an       activity.
- For example - MyApplication(which extends Application class). It is an instance of MyApplication only.

## Activity Context

- This context is available in an activity which are currently present. 
- This context is tied to the lifecycle of an activity. 
- The activity context should be used when you are passing the context in the scope of an activity or you need the context whose lifecycle is attached to the current context.
- For example - MainActivity. It is an instance of MainActivity only.

## Application Class

- The Application class in Android is the base class within an Android app that contains all other components such as activities and services.
- The Application class, or any subclass of the Application class, is instantiated before any other class when the process for your application/package is created.

## What is Intent?

- Intents are messages that can be used to pass information to the various components of android. 
- It is used to launch an activity, display a web page, send SMS, send email, etc. 
- There are two types of intents in android:
  - Implicit Intent
  - Explicit Intent
  
## What is Implicit Intent?

- By using the Implicit Intents you can communicate between various applications present in the mobile device 
  (i.e.) Implicit intent is when you call system default intent like send email, send SMS, dial number. 
- For example, you can access the current location by accessing the location data from other application also 
  (i.e.) if one application A is detecting the current location of the user then you can use the data of the user 
  (i.e.) the current location by communicating with application A.
  
## What is Explicit Intent?

- If you want communication between the components of your application only then you can use the Explicit Intents.
- Explicit Intents are used to communicate with a particular component of the same application.
- For example, if you want to launch an Activity by clicking some button on the present Activity.
  
## What is	Pending Intent?

- If you want someone to perform any Intent operation at future point of time on behalf of you, then we will use Pending Intent.
- A PendingIntent is generally used in cases were an AlarmManager needs to be executed or for Notification. 
- A PendingIntent provides a means for applications to work, even after their process exits.

## What is Intent Filter? 

- Android OS uses filters to pinpoint the set of Activities, Services, and Broadcast receivers that can handle the Intent with help of specified set of action, categories, data   scheme associated with an Intent. 
- You will use <intent-filter> element in the manifest file to list down actions, categories and data types associated with any activity, service, or broadcast receiver.
  
##  What is Sticky Intent?

- These are the Intents which sticks with Android system for future broadcast listener.
- Sticky Intents allows communication between a function and a service. 
- For example if BATTERY_LOW event occurs then that Intent will stick with Android so that any future requests for BATTERY_LOW, will return the Intent.
