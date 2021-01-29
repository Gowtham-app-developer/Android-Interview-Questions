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
    
# Activity

- An activity represents a single screen with a user interface just like window or Containers.
- Android activity is the subclass of ContextThemeWrapper class.

# Activity Lifecycle

onCreate	Called when activity is first created.
onStart	Called when activity is becoming visible to the user.
onResume	Called when activity will start interacting with the user.
onPause	Called when activity is not visible to the user.
onStop	Called when activity is no longer visible to the user.
onRestart	Called after your activity is stopped, prior to start.
onDestroy	Called before the activity is destroyed.

# Content Provider

- A content provider component supplies data from one application to others on request and such requests are handled by the methods of the ContentResolver class. 
- A content provider can use different ways to store its data and the data can be stored in a database, in files, or even over a network.

# Broadcast Receiver

- Broadcast Receivers simply respond to broadcast messages from other applications or from the system itself. 
- These messages are sometime called events or intents.
- When overriding the onReceive() method where each message is received as an Intent object parameter.
- Types of Broadcasts -> Normal Broadcasts, Ordered Broadcasts.

# Context

- It is the context of the current state of the application.
- It can be used to get information regarding the activity and application.
- It can be used to get access to resources, databases, and shared preferences, and etc.
- Both the Activity and Application classes extend the Context class.
- Types of Context -> Application Context, Activity Context

# Application Context

- This context is tied to the lifecycle of an application. 
- The application context can be used where you need a context whose lifecycle is separate from the current context or when you are passing a context beyond the scope of an       activity.
- For example - MyApplication(which extends Application class). It is an instance of MyApplication only.

# Activity Context

- This context is available in an activity which are currently present. 
- This context is tied to the lifecycle of an activity. 
- The activity context should be used when you are passing the context in the scope of an activity or you need the context whose lifecycle is attached to the current context.
- For example - MainActivity. It is an instance of MainActivity only.

# Application Class

- The Application class in Android is the base class within an Android app that contains all other components such as activities and services.
- The Application class, or any subclass of the Application class, is instantiated before any other class when the process for your application/package is created.

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

# Services & Long-running Operations

# What is services

- A Service is an application component that can perform long-running operations in the background, and it doesn't provide a user interface. 
- It can run in the background, even when the user is not interacting with your application. 
- These are the three different types of services ->Foreground Services, Background Services and Bound Services.

__Foreground Service:__ 

- A foreground service performs some operation that is noticeable to the user. 
- For example, we can use a foreground service to play an audio track. 
- A Notification must be displayed to the user.

__Background Service:__

- A background service performs an operation that isn’t directly noticed by the user. 
- In Android API level 26 and above, there are restrictions to using background services and it is recommended to use WorkManager in these cases.

__Bound Service:__ 

- A service is bound when an application component binds to it by calling bindService(). 
- A bound service offers a client-server interface that allows components to interact with the service, send requests, receive results. 
- A bound service runs only as long as another application component is bound to it.

__Unbound Service:__

- A service is started when an application component, such as an activity, starts it by calling startService(). 
- Once started, a service can run in the background indefinitely, even if the component that started it is destroyed.

# Difference between Service & Intent Service

- __Service__ is the base class for Android services that can be extended to create any service. A
- class that directly extends Service runs on the main thread so it will block the UI (if there is one) and should therefore either be used only for short tasks or should make   use of other threads for longer tasks.
- __IntentService__ is a subclass of Service that handles asynchronous requests (expressed as “Intents”) on demand. 
- Clients send requests through startService(Intent) calls. 
- The service is started as needed, handles each Intent in turn using a worker thread, and stops itself when it runs out of work.

# Difference between AsyncTasks & Threads?

- __Thread__ should be used to separate long running operations from main thread so that performance is improved. 
- But it can't be cancelled elegantly and it can't handle configuration changes of Android. 
- You can't update UI from Thread.
- __AsyncTask__ can be used to handle work items shorter than 5ms in duration. 
- With AsyncTask, you can update UI unlike java Thread. 
- But many long running tasks will choke the performance.

# Difference between Service, Intent Service, AsyncTask & Threads

- Android __service__ is a component that is used to perform operations on the background such as playing music. 
- It doesn’t has any UI (user interface). 
- The service runs in the background indefinitely even if application is destroyed.
- __AsyncTask__ allows you to perform asynchronous work on your user interface. 
- It performs the blocking operations in a worker thread and then publishes the results on the UI thread, without requiring you to handle threads and/or handlers yourself.
- __IntentService__ is a base class for Services that handle asynchronous requests (expressed as Intents) on demand. 
- Clients send requests through startService(Intent) calls; the service is started as needed, handles each Intent in turn using a worker thread, and stops itself when it runs     out of work.
- A __thread__ is a single sequential flow of control within a program. Threads can be thought of as mini-processes running within a main process.

# What are Handlers?

- Handlers are objects for managing threads. 
- It receives messages and writes code on how to handle the message. 
- They run outside of the activity’s lifecycle, so they need to be cleaned up properly or else you will have thread leaks.
- Handlers allow communicating between the background thread and the main thread.
- A Handler class is preferred when we need to perform a background task repeatedly after every x seconds/minutes.

# What is a Job Scheduling?

- Job Scheduling api, as the name suggests, allows to schedule jobs while letting the system optimize based on memory, power, and connectivity conditions.
- The JobScheduler supports batch scheduling of jobs. The Android system can combine jobs so that battery consumption is reduced. 
- JobManager makes handling uploads easier as it handles automatically the unreliability of the network. It also survives application restarts.

__Scenarios:__
- Tasks that should be done once the device is connect to a power supply
- Tasks that require network access or a Wi-Fi connection.
- Task that are not critical or user facing
- Tasks that should be running on a regular basis as batch where the timing is not critical

# How to run parallel tasks in Java or Android?

- Creating and destroying threads has a high CPU usage, so when we need to perform lots of small, simple tasks concurrently, the overhead of creating our own threads can take     up a significant portion of the CPU cycles and severely affect the final response time.
- ThreadPool consists of a task queue and a group of worker threads, which allows it to run multiple parallel instances of a task.

# How should update the UI of an activity from a background service?

- We need to register a LocalBroadcastReceiver in the activity. And send a broadcast with the data using intents from the background service. 
- As long as the activity is in the foreground, the UI will be updated from the background. Ensure to unregister the broadcast receiver in the onStop() method of the activity     to avoid memory leaks. 
- We can also register a Handler and pass data using Handlers. I have detailed a sample implementation on this.

# What is Memory Leak?

- Failure of releasing unused objects from the memory
- That means there are unused objects in the application that the garbage collector cannot release from memory. 
- So the memory unit is occupied until the end of the application/method.

# ANR

- ANR (Application Not Responding )is due to handling long running task in Main Thread(UI thread).
- If the main thread is stopped for more than 5 sec you get ANR.
- Note: Never run long running task on UI thread

# How to avoid ANRs?

- Create a different worker thread for long running operations like database operations, network operations etc.

# Crash

- Crash are due to exception and error like Nullpoint,classNotfound, typecast ,parse error etc. ANR also causes crash of application.

# Async Task

- Android application runs on a single thread when launched. 
- Due to this single thread model tasks that take longer time to fetch the response can make the application non-responsive. 
- To avoid this we use android AsyncTask to perform the heavy tasks in background on a dedicated thread and passing the results back to the UI thread. 
- Hence use of AsyncTask in android application keeps the UI thread responsive at all times.

# What are the basic methods used in an android AsyncTask class?

- __doInBackground() :__ This method contains the code which needs to be executed in background. In this method we can send results multiple times to the UI thread by publishProgress() method. 
- To notify that the background processing has been completed we just need to use the return statements
- __onPreExecute() :__ This method contains the code which is executed before the background processing starts
- __onPostExecute() :__ This method is called after doInBackground method completes processing. Result from doInBackground is passed to this method
- __onProgressUpdate() :__ This method receives progress updates from doInBackground method, which is published via publishProgress method, and this method can use this           progress update to update the UI thread

# what are The three generic types used in an android AsyncTask class?:

- __Params :__ The type of the parameters sent to the task upon execution
- __Progress :__ The type of the progress units published during the background computation
- __Result :__ The type of the result of the background computation



