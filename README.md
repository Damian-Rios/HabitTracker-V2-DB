### INF654 - Mobile Web Development
### Damian Rios
### PWA Prototype


# OnSync Habit Tracker

## Description
OnSync Habit Tracker is a Progressive Web Application (PWA) designed to help users manage and track their daily habits. Users can log activities, view their progress, and receive notifications for reminders. The application features a user-friendly interface built using HTML, CSS (Materialize), and JavaScript, with offline capabilities for uninterrupted usage.


## Getting Started

### Dependencies
- HTML5
- CSS3 (Materialize CSS Framework)
- JavaScript
- Firebase
- IndexedDB
- A web browser with PWA support

### Executing Program
1. Clone the repository: To clone, open your terminal and run the following command:

   ```bash
   git clone https://github.com/Damian-Rios/HabitTracker.git

2. Navigate to the project directory:

   ```bash
   cd HabitTracker

3. Set up a live server:
   * You can use an extension like **Live Server** in Visual Studio
   Code, or use a simple HTTP server.

4. Open the app in your browser
   * Once the server is running, open your browser and navigate to [http://localhost:5500](http://localhost:5500) (or the port number shown in your terminal).


## PWA Features
### Service Worker
The service worker caches assets for offline access and faster load times:
- Install: Caches essential files (HTML, JS, icons).
- Activate: Clears old caches to save storage.
- Fetch: Uses a cache-first strategy, serving cached files and fetching new ones as needed.

### Caching Strategy
Uses a Cache-First approach, loading assets from cache first for speed and offline access, with new files dynamically added to the cache during use.

### Web app Manifest
The manifest enables app installation with metadata such as:
- Icons: Device-optimized icons
- Theme/Background Colors: For a cohesive app-like feel
- Display Mode: Standalone mode for a native experience
- Shortcuts: Quick access to features like "Add Habit" and "Track Progress"
- And much more

## Firebase & IndexedDB Integration
### Firebase Integration
Firebase is used to store user data remotely, ensuring that users can access their habits across devices. The app utilizes Firebase's Firestore database to save user habits and logs. This integration allows seamless synchronization of data between the web and cloud, even when the app is online or offline.

- Firebase IDs: Each habit log entry is assigned a unique ID generated by Firebase, ensuring that data can be correctly associated with user accounts.
- Offline Mode: Firebase's offline capabilities ensure that any changes made while the user is offline are cached through IndexedDB and synchronized automatically once the user regains connectivity.

### IndexedDB Integration
IndexedDB is used for local storage, providing offline functionality by storing data directly on the user's device. This enables users to log habits even when they are not connected to the internet.

### CRUD Operations:
- Create: New habits and habit logs are added to IndexedDB for offline access and immediately uploaded to Firebase when a network connection is available.
- Read: Habits and habit logs are read from IndexedDB when offline and from Firebase when online.
- Update: Habits and habit logs are updated both locally in IndexedDB and in Firebase once online synchronization happens.
- Delete: Habit and habit log entries can be removed locally and will sync to Firebase once online.

### Synchronization Process
The app uses Firebase to synchronize data across devices. When the user is online, all locally made changes are uploaded to Firebase, and any updates from Firebase are downloaded to ensure consistency. If the user is offline, changes are stored in IndexedDB, and once the user reconnects, these changes are automatically synced with Firebase. This seamless synchronization ensures that users' habit data is always up to date, regardless of their internet connection.

- Maintaining Firebase IDs: When syncing data from IndexedDB to Firebase, the unique Firebase ID associated with each habit log entry ensures that the data is accurately matched and updated in the cloud database.

## Authors

Damian Rios