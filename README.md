**# Lift-Logger**
A lightweight, mobile-first Progressive Web App (PWA). Built with vanilla JavaScript and Firebase Firestore.




**#Key Features**
PWA Ready: Installable on iOS and Android for a full-screen, native app experience with offline support.
Yearly Activity Heatmap: A contribution grid to track gym consistency.
Movement Search: Client-side filtering of your workout history.

**#Setup and Config**
Feel free to fork this repository and then set up your own firebase-config.js file with the appropriate information

--Firebase Setup Steps--
1. Go to the Firebase Console and create a new project.
2. Enable Cloud Firestore in test mode or with the rules provided below.
3. Register a "Web App" in the project settings to get your configuration object.
4. Create a file named firebase-config.js in the root directory and paste your credentials:

5. To allow the app to read and write your workouts, apply these rules in the Firestore "Rules" tab:

service cloud.firestore {
  match /databases/{database}/documents {
    match /workouts/{workout} {
      allow read, write: if true; 
    }
  }
}


6. Create a Composite Index
Because the app filters by both date and movement to handle session markers, Firestore requires a composite index.

Attempt to log your first workout in the app.

Click the error link to generate and enable the required index automatically. (In the same browser you are setting up your firebase)



