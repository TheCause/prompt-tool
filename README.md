## Prompt Tool

This repository contains the prompt-tool for `MidJourney` which is currently hosted at https://prompt.noonshot.com/midjourney. 

This is an open-source project, and we encourage anyone who'd like to contribute to submit a Pull Request and help make this more valuable for others.

<img width="1343" alt="Screenshot 2022-12-20 at 9 28 31 AM" src="https://user-images.githubusercontent.com/26839654/208729037-372c1dd3-ea7a-4a12-bdf5-e3e06043490c.png">
<img width="1357" alt="Screenshot 2022-12-20 at 9 28 27 AM" src="https://user-images.githubusercontent.com/26839654/208729048-2e7178e7-dbab-4a7c-8372-35ec6019278d.png">


## Implementation

### Step 1: Fork the project

- Fork the project on GitHub

### Step 2: Get the project locally

- Clone the forked project on your local computer

### Step 3: initialize Firebase
Firebase is a real-time back-end development service developed by Google. It offers a variety of features such as database management, authentication, file storage and more. In this tutorial, we will show you how to create a new Firebase.

#### Prerequisites

- An active Google account

#### Access the Firebase console

- Access the Firebase console by logging in with your Google account at [https://console.firebase.google.com/](https://console.firebase.google.com/)

#### Create a new database

- Click on the "Create a Firebase" button
- Enter a name for your Firebase
- Select an existing project or create a new project
- Click on the "Create a database" button

#### Configure authentication

- In the "Authentication" section, click on the "Configure authentication" button
- Select the desired authentication methods : Google
- Configure the settings for each selected authentication method
- Click the "Save" button to save changes

### Step 4: Edit Firebase security rules

- Modify Firebase security rules to allow reading and writing for authenticated users

```yaml
service firebase.storage {
  match /b/{bucket}/o {
    match /{allPaths=**} {
      allow read: if request.auth != null || !request.auth;
      allow write, update, delete: if request.auth != null;
    }
  }
}
```

### Step 5: Create an .env file

- Create a new `.env` file with the Firebase connection information

```c
NEXT_PUBLIC_FIREBASE_API_KEY="YOUR_API_KEY"
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN="Project_Name.firebaseapp.com"
NEXT_PUBLIC_FIREBASE_PROJECT_ID="Project_ID"
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET="Project_Name.appspot.com"
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID="SENDER_ID"
NEXT_PUBLIC_FIREBASE_APP_ID="APP_ID",
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID="MEASUREMENT_ID"
```

### Step 6: Run NPM commands

- Run `npm install`, `npm build` and `npm run` commands to compile and run the project.

### Step 7: Access the administration interface

- Access the administration interface at `localhost:3000/midjourney/admin`.

### Step 8: Integrate data

- Integrate data in the Firebase database to be able to use the site


Original Contributors:

- https://github.com/claudfuen
- https://github.com/Marfuen

## License
MIT
