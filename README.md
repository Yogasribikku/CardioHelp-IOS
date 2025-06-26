# CardioHelp-IOS
Smart Health Application (Flutter)
This is the Flutter-based mobile application for the Smart Health project. It connects to Bluetooth Low Energy (BLE) devices to stream ECG data and uses an on-device TensorFlow Lite (TFLite) model for real-time arrhythmia detection.

Project Structure
lib/app.dart: Main application entry point, handles routing and global providers.
lib/features/auth/: Contains authentication (login/registration) screens and services.
lib/features/patient_info/: Manages patient demographic information and persistence.
lib/features/device/: Handles BLE device scanning and connection.
lib/features/ecg/: Implements ECG data visualization and AI inference.
lib/features/info/: Includes informational screens like the 'About' page.
lib/core/ble/: Core BLE service for low-level Bluetooth communication.
lib/core/ai/: Core AI service for loading and running TFLite models.
assets/models/: Directory for TensorFlow Lite model files.
Setup and Installation
Clone the repository:

git clone <your_repository_url>
cd smart_health_flutter
Ensure Flutter is installed: If you don't have Flutter installed, follow the official guide: https://flutter.dev/docs/get-started/install

Get Flutter dependencies: Navigate to the smart_health_flutter directory and run:

flutter pub get
Set up iOS (if targeting iOS): Navigate to the ios directory inside smart_health_flutter and run:

pod install
You may need to open smart_health_flutter/ios/Runner.xcworkspace in Xcode to configure signing & capabilities (e.g., Bluetooth, Location Services) for your physical device.

Running the Application
From the smart_health_flutter directory, you can run the app on an available device or simulator:

flutter run
To run on a specific device (e.g., your iPhone):

flutter run -d <your_device_id> # Use `flutter devices` to find your device ID
Core Functionality
Authentication: Users can register and log in. User data is persisted locally using sqflite.
Patient Info: Users can enter and save patient demographic data.
Device Scan: Scans for nearby Bluetooth devices and allows connection to them.
ECG Stream: Displays real-time ECG data. Includes a simulation mode for testing without a physical device.
AI Prediction: Utilizes a TFLite model (Arrhythmia on_ECG_Classification.tflite) to predict heart rhythm status (Normal, Arrhythmia, Noise) from ECG data.
Troubleshooting
flutter pub get or pod install issues: Ensure your Flutter environment is correctly set up and all paths are configured.
BLE connection problems: Check Info.plist permissions (Bluetooth usage descriptions, background modes) and ensure Location Services are enabled on iOS.
AI inference errors: Refer to the console output for AI_MODEL_LOAD_DEBUG, AI_INFERENCE_DEBUG, and AI_INFERENCE_ERROR messages to diagnose input/output shape mismatches or model loading failures.
