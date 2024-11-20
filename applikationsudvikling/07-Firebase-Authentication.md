# Firebase Authentication

https://github.com/nicklasdean/compose-firebase-auth



### Pre-requisites:

#### Follow step 1-4: Add Firebase: using the Firebase console

https://firebase.google.com/docs/android/setup

##### Note that dependencies has already been added to the gradle files

- Test your application setup by creating a user



### Exercise 1

Understand <u>HOW</u> user registration works in the sample application.

- Trace the success function from the Navigation composable to where it is executed.



Write a short summary of how user registration works in the codebase works (60. min in pairs). Answer the following questions:

- How does navigation happen between the Welcome and the Login composable?
- How does the ViewModel interact with the Login composable?
  - Why are mutablestates necessary?

- When a registration of a user is successful - how does Compose handle the navigation?



You can formulate answers like this:

- When the composable registers an ... event ...
  - Where does the data come from exactly?
  - How does functions get passed through the stack?
  - What classes / composable does data / functions get passed by?

You should **not** explain it code line-by-line but write a prose summary answering the questions.

- This is an oppertunity to gain insight and overview - please ask for help if stuck.



Aflever: https://kea-fronter.itslearning.com/ContentArea/ContentArea.aspx?LocationID=6478&LocationType=1



### Exercise 2

- Extend the feature of the app such that if a user tries to register *unsuccessfully*, the app will navigate to a "failure" page such as this:

<img src="assets/image-20240321105630115.png" alt="image-20240321105630115" style="zoom:25%;" />



### Exercise 3

- Extend the feature of the app such that Login is possible - not only registration.



### Advanced

- Extend the feature of the app such that when a user registers or logs in - their e-mail is displayed on the success-screen
  - The user information should be stored in the viewmodel and can be accessed by calling the Firebase library:

```kotlin
FirebaseAuth.getInstance().getCurrentUser()
FirebaseAuth.getInstance().currentUser?.email
```

