# Android Architecture

# What is Architecture?

- If you are building an application in an organized manner with some set of rules, describe proper functionalities and implement it with proper protocols, then it is called an Architecture.

# Android Architecture Components

- The Android Architecture Components is the collection of libraries that helps developers to design clean, robust, testable and maintainable apps. 
- Using __LiveData__ to build data objects that notify views when the underlying database changes.
- __ViewModel__ stores UI-related data that isn't destroyed on app rotations.
- __Room__ is a SQLite object mapping library. Use it to avoid boilerplate code and easily convert SQLite table data to Java objects. 
- __Data Binding__ It helps in declaratively binding UI elements to in our layout to data sources of our app.
- __WorkManager__ Manage every background jobs in Android with the circumstances we choose.

# Android Jetpack

- Android Jetpack is a collection of Android software components which helps us in building great Android apps.
- These software components help in:
    - Following the best practices and writing the boilerplate code.
    - Making complex things very simple.

# Data Binding

- The Data Binding Library is a support library that allows you to bind UI components in your layouts to data sources in your app using a declarative format rather than             programmatically.
- In other words, Android DataBinding provides a way to tie the UI with business logic (i.e.) allowing the UI values to update automatically without manual intervention. 
- This reduces lot of boilerplate code in your business logic that you usually write to sync the UI when new data is available. 

# View Model

- The ViewModel class is designed to hold and manage UI-related data in a life-cycle conscious way. 
- This allows data to survive configuration changes such as screen rotations.
- View model create in the memory when activity creates, It lives until the activity cleared from the memory. 
- So ViewModel can hold value belong to the activity.
- Adanatges -> No Memory Leak and Data will be always updated.

# Android LiveData

- LiveData is a part of the architecture patterns.
- It’s basically a data holder that contains primitive/collection types.
- It’s used for observing changes in the view and updating the view when it is ACTIVE.
- In other terms, LiveData is just a data type which notifies it’s observer whenever the data is changed. 

# How LiveData Works

- The method onChanged() would get trigger whenever the LiveData is changed.
- setvalue() runs on the main thread.
- postvalues() runs on the background thread.
- Invoking  getvalues() on the LiveData type instance would return you the current data.

# Mutable LiveData

- MutableLiveData is just a class that extends the LiveData type class.
- MutableLiveData is commonly used since it provides the  postvalues(), setvalues() methods publicly, something that LiveData class doesn’t provide.
- LiveData/MutableLiveData is commonly used in updating data in a RecyclerView from a collection type (List, Array List etc.).

# Room Database

- Room is a persistence library, part of the Android Jetpack.
- Room provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite.
- It makes it easier to work with SQLiteDatabase objects in your app, decreasing the amount of boilerplate code and verifying SQL queries at compile time.

# Components of Room

- There are having 3 components in room.

__Entity:__ 

- Instead of creating the SQLite table, we will create the Entity. Entity is nothing but a model class annotated with @Entity. 
- The variables of this class is our columns, and the class is our table.

__Database:__ 

- It is an abstract class where we define all our entities.

__DAO:__ 

- DAO Stands for Data Access Object. 
- It is an interface that defines all the operations that we need to perform in our database.

# MVC

- It is a Model-View-Controller and the most commonly used architecture. 
- These are the three components used in MVC.
- The __model__ refers to the data model classes. 
- The __view__ refers to the xml files.
- The __controller__ handles the business logic.
- Negatives could be If we change the view, the controller logic should also be changed and  Maintenance is also an issues.

# MVP

- It as Model-View-Presenter architecture. 
- View more separated from Model and the Presenter is the mediator between Model and View.
- Easier to create unit tests

