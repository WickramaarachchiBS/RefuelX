<div align="center">

# ⛽ RefuelX

### On-Demand Fuel & EV Charging Delivery Service

[![Flutter](https://img.shields.io/badge/Flutter-3.6.0-02569B?logo=flutter)](https://flutter.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Enabled-FFCA28?logo=firebase)](https://firebase.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20iOS-lightgrey)](https://flutter.dev/)

</div>

---

## 📖 About

**RefuelX** is a modern mobile application that revolutionizes the way users access fuel and EV charging services. With RefuelX, users can order fuel delivery directly to their location, find nearby fuel stations, EV charging stations, and service centers, all while enjoying seamless payment integration and real-time tracking.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🔐 **User Authentication** | Secure sign-in and registration using Firebase Authentication |
| ⛽ **Fuel Ordering** | Order fuel delivery directly to your location with real-time tracking |
| 🔌 **EV Charging Orders** | Schedule EV charging services at your convenience |
| 🗺️ **Interactive Maps** | Find nearby fuel stations, EV charging stations, and service centers using Google Maps integration |
| 💳 **Payment Integration** | Secure payment processing with Stripe (Visa, Mastercard, Amex, Discover, PayPal) |
| 🎁 **Deals & Promotions** | Access exclusive deals and promotional offers |
| 📊 **Order Summary** | Detailed order tracking and history |
| 👤 **Profile Management** | Manage user profiles and preferences |

---

## 🛠️ Tech Stack

### **Frontend**
- **Framework**: Flutter 3.6.0
- **Language**: Dart
- **UI Components**: Material Design 3, Cupertino Icons

### **Backend & Services**
- **Authentication**: Firebase Authentication
- **Database**: Cloud Firestore
- **Storage**: Firebase Storage
- **Maps**: Google Maps API
- **Payment Gateway**: Stripe

### **APIs & Integrations**
- **Maps**: Google Maps API
- **Geolocation**: Geolocator
- **Routing**: Flutter Polyline Points
- **HTTP Requests**: HTTP package
- **URL Launcher**: URL Launcher

---

## 📸 Screenshots

Screenshots are available in the `docs/screenshots/` directory.

> **Note**: Add your app screenshots to showcase the user interface and key features.

---

## 🚀 Installation

### Prerequisites

Before you begin, ensure you have the following installed:

- [Flutter SDK](https://flutter.dev/docs/get-started/install) (v3.6.0 or higher)
- [Dart SDK](https://dart.dev/get-dart)
- [Android Studio](https://developer.android.com/studio) or [Xcode](https://developer.apple.com/xcode/) (for iOS)
- [Git](https://git-scm.com/)
- A Firebase project with Firestore, Authentication, and Storage enabled
- Google Maps API key
- Stripe account with API keys

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/WickramaarachchiBS/RefuelX.git
   cd RefuelX
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Configure Firebase**
   - Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Enable Firebase Authentication (Email/Password provider)
   - Enable Cloud Firestore
   - Enable Firebase Storage
   - Download `google-services.json` (Android) and `GoogleService-Info.plist` (iOS)
   - Place them in the appropriate directories:
     - Android: `android/app/google-services.json`
     - iOS: `ios/Runner/GoogleService-Info.plist`

4. **Set up environment variables**
   
   Update `lib/constants.dart` with your API keys:
   ```dart
   const String googleMapsApiKey = 'YOUR_GOOGLE_MAPS_API_KEY';
   const String stripePublishableKey = 'YOUR_STRIPE_PUBLISHABLE_KEY';
   const String stripeSecretKey = 'YOUR_STRIPE_SECRET_KEY';
   ```

   <!-- > ⚠️ **Security Warning**: Never commit API keys to version control. Consider using environment variables or secure storage solutions for production. -->

5. **Run the application**
   ```bash
   flutter run
   ```

---

## 🎯 Usage

### Demo Credentials

For testing purposes, you can use the following credentials:

- **Email**: `banuka@gmail.com`
- **Password**: `123456`

Alternatively, create a new account using the registration flow within the app.

### Building for Production

#### Android
```bash
flutter build apk --release
```

For Android App Bundle:
```bash
flutter build appbundle --release
```

#### iOS
```bash
flutter build ios --release
```

---

## 📁 Project Structure

```
RefuelX/
├── android/                      # Android native code
├── ios/                          # iOS native code
├── assets/                       # App assets (images, fonts)
│   ├── fonts/                    # Montserrat font
│   └── *.png                     # Payment provider logos
├── lib/
│   ├── components/               # Reusable UI components
│   │   ├── bottom_widget.dart
│   │   ├── center_widgets.dart
│   │   ├── map_widget.dart
│   │   ├── navigation.dart
│   │   ├── snakbarMessagePopup.dart
│   │   └── textfield_widget.dart
│   ├── screens/                  # Application screens
│   │   ├── homeScreenContent/    # Home screen modules
│   │   │   ├── home_content.dart
│   │   │   ├── fuel_content.dart
│   │   │   ├── location_content.dart
│   │   │   └── profile_content.dart
│   │   ├── deals_screen.dart
│   │   ├── dynamic_screen.dart
│   │   ├── evcharging_order_screen.dart
│   │   ├── evstations_screen.dart
│   │   ├── fuel_order_screen.dart
│   │   ├── fuelstations_screen.dart
│   │   ├── order_summary_screen.dart
│   │   ├── payment_screen.dart
│   │   ├── paymentsuccessful_screen.dart
│   │   ├── paymentUnsuccessfull_screen.dart
│   │   ├── servicestations_screen.dart
│   │   ├── signin_screen.dart
│   │   ├── signup_screen.dart
│   │   └── welcome_screen.dart
│   ├── services/                 # Backend services
│   │   ├── firebase_auth.dart
│   │   ├── google_services.dart
│   │   └── stripe_services.dart
│   ├── constants.dart            # API keys and constants
│   └── main.dart                 # Application entry point
├── test/                         # Unit and widget tests
├── .gitignore                    # Git ignore file
├── pubspec.yaml                  # Project dependencies
└── README.md                     # Project documentation
```

---

## 🏗️ Architecture

RefuelX follows a **feature-based architecture** with separation of concerns:

- **Components**: Reusable UI widgets shared across screens
- **Screens**: Feature-specific UI implementations with navigation
- **Services**: Business logic and external API integrations
  - Firebase Authentication management
  - Google Maps and geolocation services
  - Stripe payment processing

### Key Design Patterns
- **Widget Composition**: Modular and reusable components
- **Service Layer**: Abstraction of external dependencies
- **Route-based Navigation**: Centralized route management in `main.dart`

---

## 🌐 Environment Variables

Create a `lib/constants.dart` file with the following variables:

```dart
// Google Maps API Key
const String googleMapsApiKey = 'YOUR_GOOGLE_MAPS_API_KEY';

// Stripe API Keys
const String stripePublishableKey = 'YOUR_STRIPE_PUBLISHABLE_KEY';
const String stripeSecretKey = 'YOUR_STRIPE_SECRET_KEY';
```

---

## 🧪 Testing

Run all tests:
```bash
flutter test
```

Run tests with coverage:
```bash
flutter test --coverage
```

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2026 RefuelX

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📧 Contact & Support

- **Repository**: [RefuelX on GitHub](https://github.com/WickramaarachchiBS/RefuelX)
- **Issues**: [Report a bug or request a feature](https://github.com/WickramaarachchiBS/RefuelX/issues)

---

## 🙏 Acknowledgements

- [Flutter](https://flutter.dev/) - UI toolkit for building beautiful apps
- [Firebase](https://firebase.google.com/) - Backend and authentication services
- [Google Maps Platform](https://developers.google.com/maps) - Maps and location services
- [Stripe](https://stripe.com/) - Payment processing
- [Flutter Community](https://flutter.dev/community) - For amazing packages and support

---

<div align="center">

**Made with ❤️ using Flutter**

⭐ Star this repo if you find it helpful!

</div>