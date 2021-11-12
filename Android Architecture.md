# Android Architecture Components

## Android Jetpack

-	Android Jetpack is a collection of libraries to help developers follow best practices, reduce boilerplate code and write code that works consistently across Android versions   and devices so that developers can focus on the code they care about.
-	In simple it helps in reducing the boilerplate code and making complex things very simple.

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

- LiveData is a part of the Android Architecture Components. 
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

## Work Manager

- WorkManager is a background processing library which is used to execute background tasks which should run in a guaranteed way but not necessarily immediately. 
- WorkManager we can enqueue our background processing even when the app is not running and the device is rebooted for some reason. 
- It also lets us define constraints necessary to run the task e.g. network availability before starting the background task.

## Android Architecture pattern

- An Android Architecture pattern gives modularity to the project files and assures that all the codes get covered in Unit testing. 
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

- It as Model-View-Presenter architecture. 
- View more separated from Model and the Presenter is the mediator between Model and View.
- Easier to create unit tests.

__Model__

- It is business logic and Data State. 
- Getting and manipulating the data, communicates with the presenter, interacts with the database. 
- It doesn't interact with the view.

__View__

- Consists of UI, activity, and fragment. 
- It interacts with the presenter.

__Presenter__

- The Presenter is responsible to act as the middle man between View and Model. 
- It retrieves data from the Model and returns it formatted to the View.
- But unlike the typical MVC, it also decides what happens when you interact with the View.

__Drawbacks__

- The main problem is the tight-coupling between the View and the Presenter and extra layer of difficulty while writing unit tests.
- For more visit, https://github.com/Gowtham-app-developer/MVP-using-Java#mvp-using-java

## MVVM

- MVVM stands for Model View ViewModel and it is a design pattern that is used to build softwares applications.
- MVVM helps us to separate the Business Logic of our Application from the Views or UI.
- It losses the tight coupling between each component.
- Works on the concept of observables.
- Children don't have reference to the parent, they only have reference by observables.

__Model__

- This is responsible for handling the data in the application. 
- It is business logic and Data State. 
- Model cannot directly interact with Views, but it interacts with ViewModels and then Views with the help of observables.

__View__

- This is the User Interface of our Application. 
- It should not contain any application logic.

__ViewModel__

- It is basically a link between Model and View.
- It handles the communication of the view with the rest of the application (calling the business logic classes) and exposes the states/data to whomever needs to consume it       using LiveData.

__Drawbacks__

- You have to create observables for each UI component.
- The code size is quite excessive.
- For more visit, https://github.com/Gowtham-app-developer/MVVM-using-Java#mvvm-using-java

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

## MVI

- MVI stands for Model-View-Intent.
- It works based on the principle of unidirectional and cylindrical flow inspired by the Cycle.js framework.

Model: Unlike other patterns, In MVI Model represents the state of the UI. i.e for example UI might have different states like Data Loading, Loaded, Change in UI with user Actions, Errors, User current screen position states. Each state is stored as similar to the object in the model.
View: The View in the MVI is our Interfaces which can be implemented in Activities and fragments. It means to have a container which can accept the different model states and display it as a UI. They use observable intents(Note: This doesn't represent the Android traditional Intents) to respond to user actions.
Intent: Even though this is not an Intent as termed by Android from before. The result of the user actions is passed as an input value to Intents. In turn, we can say we will be sending models as inputs to the Intents which can load it through Views.

Working

User does an action which will be an Intent → Intent is a state which is an input to model → Model stores state and send the requested state to the View → View Loads the state from Model → Displays to the user. If we observe, the data will always flow from the user and end with the user through intent. It cannot be the other way, Hence its called Unidirectional architecture. If the user does one more action the same cycle is repeated, hence it is Cyclic.

![image](https://user-images.githubusercontent.com/78175168/122943224-75359b00-d394-11eb-9f92-b30e76aba94f.png)

Advantages and Disadvantages of MVI
Let’s see what are the advantages and disadvantages of MVI

Advantages of MVI

Maintaining state is no more a challenge with this architecture, As it focuses mainly on states.
As it is unidirectional, Data flow can be tracked and predicted easily.
It ensures thread safety as the state objects are immutable.
Easy to debug, As we know the state of the object when the error occurred.
It's more decoupled as each component fulfills its own responsibility.
Testing the app also will be easier as we can map the business logic for each state.
Disadvantages of MVI

It leads to lots of boilerplate code as we have to maintain a state for each user action.
As we know it has to create lots of objects for all the states. This makes it too costly for app memory management.
Handling alert states might be challenging while we handle configuration changes. For example, if there is no internet we will show the snackbar, On configuration change, it shows the snackbar again as its the state of the intent. In terms of usability, this has to be handled.
With this background, let’s create a small app with MVI  

## What is Repository Pattern?

- The Repository pattern is useful to separate persistence concerns from rest of the application. 
- In using the Repository design pattern, you can hide the details of how the data is eventually stored or retrieved to and from the data store. This data store can be a         database, an xml file, etc. 
- This also helps improve testing ability because now, you can mock the Repository and test rest of the code easily without connection to persistence layer.

## What is Clean Code?

- Clean code can be read and enhanced by a developer other than its original author that comes With understandability comes readability, changeability, extensibility, and         maintainability.
- Code should be elegant, no duplication, Runs all the Tests, Create the meaningful Names in Classes and functions ,Minimize the number of entities such as classes, Methods and   the Functions.

## Why Design Pattern?

- Makes the code understandable.
- Makes the code maintainable for Long run.
- Makes the Project loosely coupled.
- Makes the code Testable.
- Making Changes, new Features are Easy.

