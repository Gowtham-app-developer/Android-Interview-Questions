# Android Architecture

## Android Jetpack

-	Android Jetpack is a collection of Android software components which helps us in building Android apps.
-	These software components helps in reducing the boilerplate code and making complex things very simple.

## What is Architecture?

- If you are building an application in an organized manner with some set of rules, describe proper functionalities and implement it with proper protocols, then it is called an Architecture.

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

## Room Database

- Room is a persistence library, part of the Android Jetpack.
- Room provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite.
- It makes it easier to work with SQLiteDatabase objects in your app, decreasing the amount of boilerplate code and verifying SQL queries at compile time.

## Components of Room

- There are having 3 components in room.

__Entity__ 

- Instead of creating the SQLite table, we will create the Entity. Entity is nothing but a model class annotated with @Entity. 
- The variables of this class is our columns, and the class is our table.

__Database__ 

- It is an abstract class where we define all our entities.

__DAO__ 

- DAO Stands for Data Access Object. 
- It is an interface that defines all the operations that we need to perform in our database.

## Architecture pattern

- An architecture pattern gives modularity to the project files and assures that all the codes get covered in Unit testing. 
- It makes the task easy for developers to maintain the software and to expand the features of the application in the future.

## MVC

- It is a Model-View-Controller and the most commonly used architecture. 
- MVC helps us to separates the business logic and presentation layer from each other.
- These are the three components used in MVC.

__Model__
 
- It has business logic and Data State. 
- Getting and manipulating the data, communicates with the controller, interacts with the database, sometimes update the views.

__View__

- The __View__ refers to the xml files.
- It communicates with the controller and sometimes interacts with the model. 
- It passes some dynamic views through the controller.

__Controller__

- It is Activity/Fragment.
- It communicates with view and model.
- It takes the user input from view/REST services and process request Get data from the model and passes to the view.  

__Drawbacks__

- Negatives could be If we change the view, the controller logic should also be changed and  Maintenance is also an issues.
- For more visit, https://github.com/Gowtham-app-developer/MVC-using-Java#mvc-using-java

## MVP

- In MVP, all presentation logic is pushed to the presenter. 
- MVP advocates separating business and persistence logic out of the Activity and Fragment
- The __Model__ handles the data part of our application
- The __Presenter__ acts as a bridge that connects a Model and a View.
- The __View__ is responsible for laying out views with the relevant data as instructed by the Presenter and the View never communicates with Model directly.
- The main problem is the tight-coupling between the View and the Presenter and extra layer of difficulty while writing unit tests.
- For more visit, https://github.com/Gowtham-app-developer/MVP-using-Java#mvp-using-java

## What is MVVM?

- MVVM stands for Model View ViewModel and it is a design pattern that is used to build softwares applications.
- MVVM helps us to separate the Business Logic of our Application from the Views or UI.
- It losses the tight coupling between each component.
- Works on the concept of observables.
- Children don't have reference to the parent, they only have reference by observables.
- For more visit, https://github.com/Gowtham-app-developer/MVVM-using-Java#mvvm-using-java

__Model__

- This is responsible for handling the data in the application. 
- It is business logic and Data State. 
- Model cannot directly interact with Views, but it interacts with ViewModels and then Views with the help of observables.

__View__

- This is the User Interface of our Application. 
- It should not contain any application logic.

__ViewModel__

- It is basically a link between Model and View.

## Differences between MVC and MVP

__Model View Controller__

- Controllers are behavior based and can share multiple views.
- View can communicate directly with Model

__Model View Presenter__

- View more separated from Model. 
- The Presenter is the mediator between Model and View.
- Easier to create unit tests
- Generally there is a one to one mapping between View and Presenter, with the possibility to use multiple Presenters for complex Views
- Listen to user action and model updates
- Updates model and view as well

## What is Repository Pattern?

- The Repository pattern is useful to separate persistence concerns from rest of the application. 
- In using the Repository design pattern, you can hide the details of how the data is eventually stored or retrieved to and from the data store. This data store can be a         database, an xml file, etc. 
- This also helps improve testing ability because now, you can mock the Repository and test rest of the code easily without connection to persistence layer.

## What is Clean Code?

- Clean code can be read and enhanced by a developer other than its original author that comes With understandability comes readability, changeability, extensibility, and         maintainability.
- Code should be elegant, no duplication, Runs all the Tests, Create the meaningful Names in Classes and functions ,Minimize the number of entities such as classes, Methods and   the Functions.

