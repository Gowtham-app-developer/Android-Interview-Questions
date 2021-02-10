# Android Architecture

## Android Jetpack

-	Android Jetpack is a collection of Android software components which helps us in building Android apps.
-	These software components helps in writing the boilerplate code and making complex things very simple.

## Android Architecture Components

-	The __Android Architecture Components__ is the collection of libraries that helps developers to design clean, robust, testable and maintainable apps. 
- __LiveData__ is used to build data objects that notify views when the underlying database changes.
-	__ViewModel__ stores UI-related data that isn't destroyed on app rotations.
-	__Room__ is a SQLite object mapping library and we used it to avoid boilerplate code and easily convert SQLite table data to Java objects. 
-	__Data Binding__ helps in declaratively binding UI elements to in our layout to data sources of our app.
-	__WorkManager__ manage every background jobs in Android with the circumstances we choose.

## Data Binding

- The Data Binding Library is a support library that allows you to bind UI components in your layouts to data sources in your app using a declarative format rather than             programmatically.
- Data binding has the following benefits
- 	Code is shorter, easier to read, and easier to maintain than code that uses findByView().
- Data and views are clearly separated. This benefit of data binding becomes increasingly important later in this course.
- The Android system only traverses the view hierarchy once to get each view, and it happens during app startup, not at runtime when the user is interacting with the app.
- You get type safety for accessing views. (Type safety means that the compiler validates types while compiling, and it throws an error if you try to assign the wrong type to a     variable.
