
# Services & Threads

## Services

- A Service is an application component that can perform long-running operations in the background and it doesn't provide a user interface. 
- It can run in the background, even when the user is not interacting with your application. 
- For example, a service might play music in the background while the user is in a different application.
- These are the three different types of services -> Foreground Services, Background Services and Bound Services.

## Foreground Service 

- A foreground service performs some operation that is noticeable to the user. 
- For example, we can use a foreground service to play an audio track a notification must be displayed to the user.

## Background Service

- A background service performs an operation that isn’t directly noticed by the user. 
- In Android API level 26 and above, there are restrictions to using background services and it is recommended to use WorkManager in these cases.

## Bound Service

- A service is bound when an application component binds to it by calling bindService(). 
- A bound service offers a client-server interface that allows components to interact with the service, send requests, receive results. 
- A bound service runs only as long as another application component is bound to it.

## Started Service / Unbound Service

- A service is started when an application component, such as an activity, starts it by calling startService(). 
- Once started, a service can run in the background indefinitely, even if the component that started it is destroyed.

![image](https://user-images.githubusercontent.com/78175168/123263533-b0f86e00-d516-11eb-99e9-a9b17af3e358.png)

## Started Service

- __Intent Service__ is used to perform one time task i.e when the task completes the service destroys itself.
- __Intent Service__ gets  starts by calling startService().  
- __IntentService__ Implicitly calls stopself() to destroy.
- __Intent Service__ is independent of the component in which it is started.

## Difference between Service & Intent Service

- __Unbounded Service__ is used to perform long repetitive task	 
- __Bounded Service__ is used to perform background task in bound with another component	
- __Intent Service__ is used to perform one time task i.e when the task completes the service destroys itself.
- __Unbound Service__ gets starts by calling startService().	
- __Bounded Service__ gets starts by calling bindService().	
- __Intent Service__ gets  starts by calling startService().
- __Unbound Service__ is stopped or destroyed explicitly  by calling stopService().	
- __Bounded Service__ is unbind or destroyed by calling unbindService().	
- __IntentService__ Implicitly calls stopself() to destroy
- __Unbound Service__ is independent of the component in which it is started.	
- __Bound Service__ dependents on the component in which it is started.	
- __Intent Service__ is independent of the component in which it is started.

## Async Task

- Android application runs on a single thread when launched. 
- Due to this single thread model tasks that take longer time to fetch the response can make the application non-responsive. 
- To avoid this we use android AsyncTask to perform the heavy tasks in background on a dedicated thread and passing the results back to the UI thread. 
- Hence use of AsyncTask in android application keeps the UI thread responsive at all times.

## What are the basic methods used in an android AsyncTask class?

- __doInBackground() :__ This method contains the code which needs to be executed in background. 
- In this method we can send results multiple times to the UI thread by publishProgress() method. 
- To notify that the background processing has been completed we just need to use the return statements
- __onPreExecute() :__ This method contains the code which is executed before the background processing starts
- __onPostExecute() :__ This method is called after doInBackground method completes processing. Result from doInBackground is passed to this method
- __onProgressUpdate() :__ This method receives progress updates from doInBackground method, which is published via publishProgress method, and this method can use                                                                   this progress update to update the UI thread

## what are the three generic types used in an android AsyncTask class?

- __Params :__ The type of the parameters sent to the task upon execution
- __Progress :__ The type of the progress units published during the background computation
- __Result :__ The type of the result of the background computation

## What are the Advantages of using AsyncTask

- Provides generic solution for all network calls
- Publish progress to UI while executing.
- Run Asynchronously
- Easy to maintain and read.

## Problems in AysncTask

- When you rotate your screen, Activity gets destroyed, so AsyncTask will not have a valid reference to publish data from onPostExecute(). 
- In order to retain it, you need to usesetRetainState(true) if calling from fragment or onConfigChanges() if calling from activity method of an activity.
- If activity gets finished, AsyncTask execution will not cancelled automatically, you need to cancel them else they will keep on running in the background.
- If any exception occurs while performing network task, you need to handle them manually.

## What are Handlers?

- A thread must be created to execute long running jobs.
- Handlers are objects for managing threads. 
- A Handler is very convenient object to communicate between 2 threads (for instance : a background thread need to update the UI. You can use a Handler to post                                                                      some Runnable from your background thread to the UI thread).

## Android Threading

- When an application is launched in Android, it creates the first thread of execution, known as the “main” thread. 
- The main thread is responsible for dispatching events to the appropriate user interface widgets as well as communicating with components from the Android UI toolkit.
- To keep your application responsive, it is essential to avoid using the main thread to perform any operation that may end up keeping it blocked.

## Difference between AsyncTasks & Threads?

- __Thread__ should be used to separate long running operations from main thread so that performance is improved. 
- But it can't be cancelled elegantly and it can't handle configuration changes of Android. 
- You can't update UI from Thread.
- __AsyncTask__ can be used to handle work items shorter than 5ms in duration. 
- With AsyncTask, you can update UI unlike java Thread. 
- But many long running tasks will choke the performance.

## Difference between Service, Intent Service, AsyncTask & Threads

- Android __service__ is a component that is used to perform operations on the background such as playing music. 
- It doesn’t has any UI (user interface). 
- The service runs in the background indefinitely even if application is destroyed.
- __AsyncTask__ allows you to perform asynchronous work on your user interface. 
- It performs the blocking operations in a worker thread and then publishes the results on the UI thread, without requiring you to handle threads and/or handlers yourself.
- __IntentService__ is a base class for Services that handle asynchronous requests (expressed as Intents) on demand. 
- Clients send requests through startService(Intent) calls; the service is started as needed, handles each Intent in turn using a worker thread, and stops itself when it runs out of work.
- A __thread__ is a single sequential flow of control within a program. 
- Threads can be thought of as mini-processes running within a main process.

## What is a Job Scheduling?

- Job Scheduling api, as the name suggests, allows to schedule jobs while letting the system optimize based on memory, power, and connectivity conditions.
- The JobScheduler supports batch scheduling of jobs. The Android system can combine jobs so that battery consumption is reduced. 
- JobManager makes handling uploads easier as it handles automatically the unreliability of the network. It also survives application restarts.

__Scenarios:__
- Tasks that should be done once the device is connect to a power supply
- Tasks that require network access or a Wi-Fi connection.
- Task that are not critical or user facing
- Tasks that should be running on a regular basis as batch where the timing is not critical

## How to run parallel tasks in Java or Android?

- Creating and destroying threads has a high CPU usage, so when we need to perform lots of small, simple tasks concurrently, the overhead of creating our own threads can take     up a significant portion of the CPU cycles and severely affect the final response time.
- ThreadPool consists of a task queue and a group of worker threads, which allows it to run multiple parallel instances of a task.

## How should update the UI of an activity from a background service?

- We need to register a LocalBroadcastReceiver in the activity. And send a broadcast with the data using intents from the background service. 
- As long as the activity is in the foreground, the UI will be updated from the background. Ensure to unregister the broadcast receiver in the onStop() method of the activity     to avoid memory leaks. 
- We can also register a Handler and pass data using Handlers. I have detailed a sample implementation on this.

## What is Memory Leak?

- Failure of releasing unused objects from the memory
- That means there are unused objects in the application that the garbage collector cannot release from memory. 
- So the memory unit is occupied until the end of the application/method.

## ANR

- ANR (Application Not Responding )is due to handling long running task in Main Thread(UI thread).
- If the main thread is stopped for more than 5 sec you get ANR.
- Note: Never run long running task on UI thread

## How to avoid ANRs?

- Create a different worker thread for long running operations like database operations, network operations etc.

## Crash

- Crash are due to exception and error like Nullpoint,classNotfound, typecast ,parse error etc. ANR also causes crash of application.

