# RoadGuardian AI - Advanced Flutter Road Safety App

A comprehensive Flutter application for road safety monitoring featuring driver fatigue detection, driving behavior analysis, crash detection, and emergency SOS functionality.

## 🚀 Features

✅ **Authentication** - Firebase Email/Password auth with secure login/signup
✅ **Splash Screen** - Beautiful animated loading screen with auto-navigation  
✅ **Home Dashboard** - Real-time risk score, speed, weather, and safety status
✅ **Driver Fatigue Detection** - ML Kit-powered eye closure and yawning detection
✅ **Driving Behavior Monitoring** - GPS tracking, speed monitoring, braking detection
✅ **Crash Detection** - Accelerometer-based crash detection with SOS trigger
✅ **Emergency SOS** - One-click emergency contact notification with location sharing
✅ **Nearest Hospitals** - Google Maps integration showing nearby medical facilities
✅ **Settings** - Theme switching, language selection, alert preferences
✅ **Material Design 3** - Modern UI with light and dark themes

## 📱 Project Structure

```
lib/
├── main.dart                              # App entry point
├── config/
│   └── theme_config.dart                 # Material Design 3 themes
├── models/
│   ├── user_model.dart
│   ├── location_model.dart
│   ├── hospital_model.dart
│   └── emergency_contact_model.dart
├── providers/
│   ├── auth_provider.dart               # Firebase auth logic
│   └── theme_provider.dart              # Light/dark mode
├── router/
│   └── app_router.dart                  # Go Router navigation
├── screens/
│   ├── splash_screen.dart
│   ├── auth/
│   │   ├── login_screen.dart
│   │   └── signup_screen.dart
│   ├── home/
│   │   └── home_screen.dart
│   ├── driver_fatigue/
│   │   └── fatigue_detection_screen.dart
│   ├── driving_behavior/
│   │   └── driving_behavior_screen.dart
│   ├── hospitals/
│   │   └── hospitals_screen.dart
│   └── settings/
│       └── settings_screen.dart
└── widgets/
    └── dashboard_card.dart
```

## 🔧 Technical Stack

- **Flutter 3.x** - Cross-platform UI framework
- **Firebase** - Backend services
  - Authentication
  - Cloud Firestore
  - Storage
- **Google Maps** - Location-based features
- **ML Kit** - Face detection for fatigue monitoring
- **Provider** - State management
- **Go Router** - Navigation
- **Geolocator** - GPS tracking
- **Camera** - Front camera access
- **Sensors Plus** - Accelerometer data
- **Material Design 3** - Modern design system

## 📋 Prerequisites

- Flutter SDK 3.0+
- Android SDK API 21+
- Firebase Project
- Google Maps API Key
- Android Studio or VS Code

## 🚀 Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/Arya1881/Road-Safety.git
cd Road-Safety
git checkout roadguardian-ai
```

### 2. Firebase Configuration

#### Create Firebase Project
1. Go to [Firebase Console](https://console.firebase.google.com)
2. Create new project "RoadGuardian"
3. Enable Google Analytics (optional)

#### Register Android App
1. Click "Add app" → Select Android
2. Package name: `com.example.road_guardian`
3. Download `google-services.json`
4. Copy to `android/app/` directory

#### Enable Firebase Services
1. **Authentication** → Enable Email/Password
2. **Firestore** → Create database (production mode)
3. **Storage** → Enable storage bucket

### 3. Google Maps Setup

#### Get API Key
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create project: "RoadGuardian"
3. Enable APIs: Maps SDK for Android
4. Create Android API Key

#### Update Configuration
1. Edit `android/app/src/main/AndroidManifest.xml`:
```xml
<meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="YOUR_GOOGLE_MAPS_API_KEY" />
```

2. Edit `lib/firebase_options.dart`:
```dart
static const FirebaseOptions android = FirebaseOptions(
  apiKey: 'YOUR_ANDROID_API_KEY',
  appId: 'YOUR_ANDROID_APP_ID',
  messagingSenderId: 'YOUR_MESSAGING_SENDER_ID',
  projectId: 'YOUR_PROJECT_ID',
  storageBucket: 'YOUR_STORAGE_BUCKET',
);
```

### 4. Install Dependencies

```bash
flutter pub get
```

### 5. Run the App

```bash
# Debug mode
flutter run

# Release mode
flutter run --release

# Specific device
flutter run -d <device-id>
```

## 📡 API Integration

### Authentication
```dart
// Login
await authProvider.login(
  email: 'user@example.com',
  password: 'password'
);

// Signup
await authProvider.signup(
  email: 'user@example.com',
  password: 'password',
  name: 'John Doe'
);
```

### Location Services
```dart
// Get current location
final position = await Geolocator.getCurrentPosition();

// Track location
Geolocator.getPositionStream().listen((position) {
  // Update location
});
```

## 🗺️ Navigation Routes

```
/ → Splash Screen
/login → Login Screen
/signup → Signup Screen
/home → Home Dashboard
/fatigue-detection → Fatigue Detection
/driving-behavior → Driving Behavior
/hospitals → Nearby Hospitals
/settings → Settings
```

## ⚙️ Android Permissions

Required permissions (auto-added via AndroidManifest.xml):
- INTERNET
- ACCESS_FINE_LOCATION
- ACCESS_COARSE_LOCATION
- CAMERA
- BODY_SENSORS
- READ_PHONE_STATE
- WAKE_LOCK

## 🏗️ Build Commands

### Build APK
```bash
flutter build apk --release
```

### Build App Bundle
```bash
flutter build appbundle --release
```

### Clean Build
```bash
flutter clean
flutter pub get
flutter run
```

## 🐛 Troubleshooting

### Firebase Connection Issues
- Verify `google-services.json` in `android/app/`
- Check Firebase project settings
- Ensure Android package name matches

### Camera Not Working
- Check AndroidManifest permissions
- Test on physical device
- Enable location services

### Maps Not Showing
- Verify Google Maps API key
- Check SHA-1 certificate
- Ensure Maps SDK enabled in Google Cloud

## 📊 Performance Tips

- Use `const` constructors where possible
- Lazy load heavy widgets
- Cache images and data
- Minimize widget rebuilds with Provider
- Use appropriate FutureBuilders

## 🔐 Security Best Practices

- Never commit `google-services.json` with real keys
- Use environment variables for sensitive data
- Validate user input
- Encrypt stored data
- Use HTTPS for API calls

## 📈 Future Enhancements

1. **Advanced ML**
   - Better drowsiness detection
   - Road condition analysis
   - Traffic pattern recognition

2. **Cloud Features**
   - Real-time data sync
   - Cloud backup
   - Historical analytics

3. **Social Features**
   - Driver rating system
   - Safety alerts sharing
   - Community feedback

4. **Hardware Integration**
   - Smartwatch support
   - Connected vehicle APIs
   - Wearable sensors

## 📝 Code Style

- Follow [Dart Style Guide](https://dart.dev/guides/language/effective-dart/style)
- Use meaningful variable names
- Add comments for complex logic
- Format with `dart format`

## 📄 License

MIT License - See LICENSE file

## 👤 Author

**Arya1881** - [GitHub](https://github.com/Arya1881)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📞 Support

For issues and questions:
1. Check existing GitHub issues
2. Create new issue with detailed description
3. Include logs and device info

---

**Version**: 1.0.0  
**Last Updated**: 2026-05-31  
**Flutter Version**: 3.0+  
**Dart Version**: 3.0+

Made with ❤️ for safe roads
