# Otzar App

**Otzar App** is a modern and versatile Flutter application designed to provide users with a secure and seamless experience. It leverages advanced on-device capabilities to ensure high performance and reliability.

## Features

This application integrates the following key features:
- **GetX State Management:** Efficient state management, dependency injection, and routing.
- **Camera & Image Picker:** Take photos or pick images directly from the gallery.
- **Location & Compass (Geolocator & Compass):** Access precise GPS coordinates and directional data.
- **Biometric Security (Local Auth):** Secure login through fingerprint or face unlock.
- **Machine Learning (TFLite Flutter):** On-device AI processing and classification.
- **Offline Data Storage (Get Storage):** Persistent local storage for offline capabilities.
- **GIS Map & Field Test:** Dedicated modules for mapping and field analysis.

## Detailed Project Architecture

The project follows a highly modular architecture using the **GetX pattern**. Here is the complete file-level breakdown of the `lib` directory:

```text
lib/
├── main.dart
├── otzar_app.dart
└── app/
    ├── core/
    │   ├── bindings/
    │   │   └── initial_binding.dart
    │   ├── theme/
    │   │   ├── app_colors.dart
    │   │   ├── app_theme.dart
    │   │   └── app_typography.dart
    │   ├── utils/
    │   │   └── responsive_util.dart
    │   ├── values/
    │   │   ├── app_assets.dart
    │   │   ├── app_dimensions.dart
    │   │   └── app_strings.dart
    │   └── widgets/
    │       ├── offline_mode_sheet.dart
    │       ├── otzar_cached_image.dart
    │       ├── otzar_dialog.dart
    │       └── specimen_details_sheet.dart
    ├── data/
    │   ├── constants/
    │   │   └── api_endpoints.dart
    │   ├── models/
    │   │   ├── api_response_model.dart
    │   │   ├── auth_response_model.dart
    │   │   ├── email_submit_response_model.dart
    │   │   ├── mineral_model.dart
    │   │   └── user_model.dart
    │   ├── repositories/
    │   │   ├── auth_repository.dart
    │   │   └── user_repository.dart
    │   └── services/
    │       ├── api_client.dart
    │       ├── face_auth_service.dart
    │       ├── neural_model_sync_service.dart
    │       ├── storage_service.dart
    │       └── tflite_classifier_service.dart
    ├── modules/
    │   ├── email_access/
    │   │   ├── bindings/
    │   │   │   └── email_access_binding.dart
    │   │   ├── controllers/
    │   │   │   └── email_access_controller.dart
    │   │   └── views/
    │   │       └── email_access_view.dart
    │   ├── export_hub/
    │   │   ├── bindings/
    │   │   │   └── export_hub_binding.dart
    │   │   ├── controllers/
    │   │   │   └── export_hub_controller.dart
    │   │   └── views/
    │   │       └── export_hub_view.dart
    │   ├── field_test/
    │   │   ├── bindings/
    │   │   │   └── field_test_binding.dart
    │   │   ├── controllers/
    │   │   │   └── field_test_controller.dart
    │   │   └── views/
    │   │       └── field_test_view.dart
    │   ├── gis_map/
    │   │   ├── bindings/
    │   │   │   └── gis_map_binding.dart
    │   │   ├── controllers/
    │   │   │   └── gis_map_controller.dart
    │   │   ├── views/
    │   │   │   └── gis_map_view.dart
    │   │   └── widgets/
    │   │       └── gis_map_painter.dart
    │   ├── help_center/
    │   │   ├── bindings/
    │   │   │   └── help_center_binding.dart
    │   │   ├── controllers/
    │   │   │   └── help_center_controller.dart
    │   │   └── views/
    │   │       └── help_center_view.dart
    │   ├── home/
    │   │   ├── bindings/
    │   │   │   └── home_binding.dart
    │   │   ├── controllers/
    │   │   │   └── home_controller.dart
    │   │   ├── views/
    │   │   │   └── home_view.dart
    │   │   └── widgets/
    │   │       ├── hero_scan_card.dart
    │   │       └── hud_bar_widget.dart
    │   ├── logging/
    │   │   ├── bindings/
    │   │   │   └── logging_binding.dart
    │   │   ├── controllers/
    │   │   │   └── logging_controller.dart
    │   │   └── views/
    │   │       └── logging_view.dart
    │   ├── main_nav/
    │   │   ├── bindings/
    │   │   │   └── main_nav_binding.dart
    │   │   ├── controllers/
    │   │   │   └── main_nav_controller.dart
    │   │   ├── views/
    │   │   │   └── main_nav_view.dart
    │   │   └── widgets/
    │   │       └── custom_bottom_nav.dart
    │   ├── onboarding/
    │   │   ├── bindings/
    │   │   │   └── onboarding_binding.dart
    │   │   ├── controllers/
    │   │   │   └── onboarding_controller.dart
    │   │   └── views/
    │   │       └── onboarding_view.dart
    │   ├── pin_access/
    │   │   ├── bindings/
    │   │   │   └── pin_access_binding.dart
    │   │   ├── controllers/
    │   │   │   └── pin_access_controller.dart
    │   │   └── views/
    │   │       └── pin_access_view.dart
    │   ├── processing/
    │   │   ├── bindings/
    │   │   │   └── processing_binding.dart
    │   │   ├── controllers/
    │   │   │   └── processing_controller.dart
    │   │   └── views/
    │   │       └── processing_view.dart
    │   ├── profile/
    │   │   ├── bindings/
    │   │   │   └── profile_binding.dart
    │   │   ├── controllers/
    │   │   │   └── profile_controller.dart
    │   │   └── views/
    │   │       └── profile_view.dart
    │   ├── result/
    │   │   ├── bindings/
    │   │   │   └── result_binding.dart
    │   │   ├── controllers/
    │   │   │   └── result_controller.dart
    │   │   └── views/
    │   │       └── result_view.dart
    │   ├── scanner/
    │   │   ├── bindings/
    │   │   │   └── scanner_binding.dart
    │   │   ├── controllers/
    │   │   │   └── scanner_controller.dart
    │   │   └── views/
    │   │       └── scanner_view.dart
    │   ├── splash/
    │   │   ├── bindings/
    │   │   │   └── splash_binding.dart
    │   │   ├── controllers/
    │   │   │   └── splash_controller.dart
    │   │   └── views/
    │   │       └── splash_view.dart
    │   ├── sync_engine/
    │   │   ├── bindings/
    │   │   │   └── sync_engine_binding.dart
    │   │   ├── controllers/
    │   │   │   └── sync_engine_controller.dart
    │   │   └── views/
    │   │       └── sync_engine_view.dart
    │   └── vault/
    │       ├── bindings/
    │       │   └── vault_binding.dart
    │       ├── controllers/
    │       │   └── vault_controller.dart
    │       └── views/
    │           └── vault_view.dart
    └── routes/
        ├── app_pages.dart
        └── app_routes.dart
```

## Tech Stack & Packages

The project utilizes the following key dependencies:
- `get` (State Management & Navigation)
- `camera` & `image_picker` (Camera integration)
- `geolocator`, `geocoding` & `flutter_compass` (Location & mapping services)
- `local_auth` (Biometric Authentication)
- `tflite_flutter` (Machine Learning)
- `get_storage` (Local key-value Storage)

## Design & Typography

The application features a clean, responsive UI. 
Primary fonts used:
- **Poppins**
- **Inter**

## How to Run

If you have Flutter installed on your machine, follow these steps to run the application:

1. Clone the repository:
   ```bash
   git clone <repository_url>
   ```
2. Navigate to the project directory:
   ```bash
   cd otza_flutter_app
   ```
3. Install dependencies:
   ```bash
   flutter pub get
   ```
4. Run the app:
   ```bash
   flutter run
   ```

## Asset Management
The `assets/` folder contains essential static files, including images, fonts, mock data, and TensorFlow Lite (`.tflite`) machine learning models.

---
**Otzar App** - Empowering field capabilities with advanced technology!
