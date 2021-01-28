# Intents and Broadcasting

# What is intent?

- It is a kind of message or information that is passed to the components. 
- It is used to launch an activity, display a web page, send SMS, send email, etc. 
- There are two types of intents in android:
  - Implicit Intent
  - Explicit Intent
  
# What is Explicit Intent?
- If you want communication between the components of your application only then you can use the Explicit Intents.
- Explicit Intents are used to communicate with a particular component of the same application.
- For example, if you want to launch an Activity by clicking some button on the present Activity.

	Implicit Intent - By using the Implicit Intents you can communicate between various applications present in the mobile device. 
	For example, you can access the current location by accessing the location data from other application also i.e. if one application A is detecting the current location of the user then you can use the data of the user i.e. the current location by communicating with application A.
	Pending Intent – If you want someone to perform any Intent operation at future point of time on behalf of you, then we will use Pending Intent.
	A PendingIntent is generally used in cases were an AlarmManager needs to be executed or for Notification (that we’ll implement later in this tutorial). 
	A PendingIntent provides a means for applications to work, even after their process exits.
	Intent Filter – Android OS uses filters to pinpoint the set of Activities, Services, and Broadcast receivers that can handle the Intent with help of specified set of action, categories, data scheme associated with an Intent. 
	You will use <intent-filter> element in the manifest file to list down actions, categories and data types associated with any activity, service, or broadcast receiver.
	Sticky Intent– Sticky Intents allows communication between a function and a service. sendStickyBroadcast() performs a sendBroadcast(Intent) known as sticky, i.e. the Intent you are sending stays around after the broadcast is complete, so that others can quickly retrieve that data through the return value of registerReceiver(Broadcast Receiver, Intent Filter). 

	For example, if you take an intent for ACTION_BATTERY_CHANGED to get battery change events: When you call registerReceiver () for that action — even with a null BroadcastReceiver — you get the Intent that was last Broadcast for that action. Hence, you can use this to find the state of the battery without necessarily registering for all future state changes in the battery.
