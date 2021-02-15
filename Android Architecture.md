# Android Architecture

## Android Jetpack

-	Android Jetpack is a collection of Android software components which helps us in building Android apps.
-	These software components helps in reducing the boilerplate code and making complex things very simple.

## Android Architecture Components

-	The __Android Architecture Components__ is the collection of libraries that helps developers to design clean, robust, testable and maintainable apps. 
- __LiveData__ is used to build data objects that notify views when the underlying database changes.
-	__ViewModel__ stores UI-related data that isn't destroyed on app rotations.
-	__Room__ is a SQLite object mapping library and we used it to avoid boilerplate code and easily convert SQLite table data to Java objects. 
-	__Data Binding__ helps in declaratively binding UI elements to in our layout to data sources of our app.
-	__WorkManager__ manage every background jobs in Android with the circumstances we choose.

## Data Binding

- The Data Binding Library is a support library that allows you to bind UI components in your layouts to data sources in your app using a declarative format rather than           programmatically.
- Data binding has the following benefits (i.e.) Code is shorter and easier to read, Easier to maintain than code, Removes the lot of boilerplate code, Data and views are         clearly   separated.

## View Model

-	The ViewModel is a part of Android Architecture Components. 
- The ViewModel class is designed to hold and manage UI-related data in a life-cycle conscious way. 
- This allows data to survive configuration changes such as screen rotations.
- View model create in the memory when activity creates, it lives until the activity cleared from the memory and So ViewModel can hold value belong to the activity.

__Advantages of using ViewModel__

- Live through the configuration changes- If any configuration changes the data will live in ViewModel.
- No worry about leak memory
- Data will be always updated – If API is calling data from remote server the data will always update.
- Data will wait for you- If you call any APIs and that time you will rotate the phone and result delivered before activity recreation data will store in ViewModel and wait for   the re-creation of activity

## Android LiveData

- LiveData is a part of the architecture patterns.
- It’s basically a data holder that contains primitive/collection types.
- It’s used for observing changes in the view and updating the view when it is ACTIVE.
- In simple terms, LiveData is just a data type which notifies it’s observer whenever the data is changed. 
- LiveData is like a data changed notifier.

__How it Works__

- The method onChanged() would get trigger whenever the LiveData is changed.
- setvalue() runs on the main thread.
- postvalues() runs on the background thread.
- Invoking  getvalues() on the LiveData type instance would return you the current data.

## Mutable LiveData

- MutableLiveData is just a class that extends the LiveData type class.
- MutableLiveData is commonly used since it provides the  postvalues(), setvalues() methods publicly, something that LiveData class doesn’t provide.
- LiveData/MutableLiveData is commonly used in updating data in a RecyclerView from a collection type (List, Array List etc.)

## What is MVC?
- It is a Model-View-Controller.
-	The most commonly used architecture. 
-	These are the three components used in MVC -> Model, View and Controller.

## Model
- It is business logic and Data State. 
- Getting and manipulating the data, communicates with the controller, interacts with the database, sometimes update the views.

## View
- User Interface consists of XML. 
- It communicates with the controller and sometimes interacts with the model. 
- It passed some dynamic views through the controller.

## Controller: 

- It is Activity/Fragment. 
- It communicates with view and model. 
- It takes the user input from view/REST services. 
- Process request Get data from the model and passes to the view.

__Advantages__

- It keeps business logic separate in the model.
- Support asynchronous techniques
- The modification does not affect the entire model.
- Faster development process.

__Disadvantages__

- Due to large code controller is unmanageable.
- Hinders the Unit testing.
- Increased Complexity.



