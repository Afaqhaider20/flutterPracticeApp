# FeedbackApp

A simple Flutter app for sending and receiving feedback between users. It includes authentication, a flow to send structured feedback, and a screen to view feedback you’ve received.

## Features
- Login and registration with email/password
- Forgot password flow
- Send feedback to selected recipients
- View received feedback
- Basic skills/topics menu to categorize feedback

## Tech Stack
- Flutter (Dart)
- Firebase (Auth + Cloud Firestore)

## Getting Started
1. Prerequisites
   - Flutter SDK installed
   - Android Studio / Xcode set up for device emulators
   - A Firebase project (Auth + Firestore)

2. Install dependencies
```bash
flutter pub get
```

3. Firebase setup
- Android: place your `google-services.json` in `android/app/` (already present in this repo if configured).
- iOS: add `GoogleService-Info.plist` to `ios/Runner/` and ensure it’s added to the Xcode project.
- Enable Email/Password in Firebase Authentication.
- Create a Cloud Firestore database in production or test mode.

4. Run the app
```bash
flutter run
```

## Project Structure (high level)
- [lib/main.dart](lib/main.dart): App entry point
- [lib/src/app.dart](lib/src/app.dart): Root app widget
- BLoC state management:
  - [lib/src/blocs/login_bloc.dart](lib/src/blocs/login_bloc.dart)
  - [lib/src/blocs/register_bloc.dart](lib/src/blocs/register_bloc.dart)
  - [lib/src/blocs/send_feedback_bloc.dart](lib/src/blocs/send_feedback_bloc.dart)
  - [lib/src/blocs/received_feedback_bloc.dart](lib/src/blocs/received_feedback_bloc.dart)
- Data layer:
  - [lib/src/data/resources/firestore_provider.dart](lib/src/data/resources/firestore_provider.dart)
  - [lib/src/data/resources/repository.dart](lib/src/data/resources/repository.dart)
- UI screens:
  - [lib/src/ui/login.dart](lib/src/ui/login.dart)
  - [lib/src/ui/registration.dart](lib/src/ui/registration.dart)
  - [lib/src/ui/forgot_password.dart](lib/src/ui/forgot_password.dart)
  - [lib/src/ui/send_feedback.dart](lib/src/ui/send_feedback.dart)
  - [lib/src/ui/received_feedback.dart](lib/src/ui/received_feedback.dart)

## Notes
- If you change Firebase project settings, re-download the Android/iOS config files and place them in the correct folders.
- For release builds, configure app signing and update app identifiers in Android and iOS project settings.

## Troubleshooting
- If Firebase calls fail, confirm your Firebase rules and config files are correct.
- Run `flutter doctor` to verify your environment.

Enjoy building with FeedbackApp!
