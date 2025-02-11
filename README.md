# Firebase Database Initialization Error
This repository demonstrates a common error when working with Firebase's Realtime Database or Firestore: attempting to access the database before it's fully initialized.  The `bug.js` file shows the erroneous code, while `bugSolution.js` provides the corrected implementation.

## Problem
Accessing Firebase database references before the Firebase app has completely initialized (e.g., before authentication is complete) will lead to errors.  This often happens if database interactions are placed within the component's constructor or prematurely in other lifecycle methods.

## Solution
Ensure that all database operations occur *after* the Firebase application is initialized and the user is authenticated.  This typically involves using a lifecycle method like `componentDidMount` in React or equivalent in other frameworks. Wait for the `onAuthStateChanged` listener to resolve before interacting with the database.
