# Drachma Bank - Digital Banking MVP

A simple, modern banking application built with HTML, CSS, JavaScript, and Firebase. This MVP includes user authentication, balance management, and basic transaction functionality.

## Features

- 🔐 **User Authentication**: Secure registration and login with Firebase Auth
- 💰 **Balance Management**: Real-time balance tracking and updates
- 📊 **Transaction History**: Deposit and withdrawal functionality
- 📱 **Responsive Design**: Works on desktop and mobile devices
- 🎨 **Modern UI**: Clean, professional interface with smooth animations

## Setup Instructions

### 1. Firebase Configuration

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project
3. Enable Authentication (Email/Password)
4. Enable Firestore Database
5. Copy your Firebase configuration
6. Replace the placeholder config in `index.html`:

```javascript
const firebaseConfig = {
    apiKey: "your-api-key",
    authDomain: "your-project.firebaseapp.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "123456789",
    appId: "your-app-id"
};
```

### 2. Firestore Security Rules

Set up these security rules in your Firestore database:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```

### 3. GitHub Pages Deployment

1. Push this repository to GitHub
2. Go to repository Settings > Pages
3. Select "Deploy from a branch"
4. Choose "main" branch and "/ (root)" folder
5. Your app will be available at `https://yourusername.github.io/drachma`

## Usage

1. **Create Account**: Register with email and password
2. **Login**: Sign in with your credentials
3. **View Balance**: See your current account balance
4. **Deposit**: Add money to your account
5. **Withdraw**: Remove money from your account (if sufficient funds)

## Security Features

- Email/password authentication
- User-specific data isolation
- Balance validation for withdrawals
- Secure Firebase backend

## Technologies Used

- HTML5
- CSS3 (with Flexbox and Grid)
- Vanilla JavaScript (ES6+)
- Firebase Authentication
- Cloud Firestore
- Font Awesome Icons

## Browser Support

- Chrome (recommended)
- Firefox
- Safari
- Edge

## License

MIT License - feel free to use this project for learning and development purposes.
