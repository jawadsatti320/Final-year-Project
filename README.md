# OCT Eye Disease Detector (ver_1.0)

## What this package contains
- Minimal Flutter project skeleton (pubspec, lib, assets, README).
- The app is set to a **dark medical theme**, uses **gallery-only** image input,
  automatically resizes images to **300x300**, and predicts one of five classes:
  `AMD, DME, RVO, ERM, Normal` (top-1 + confidence).

## IMPORTANT - Add your model
1. Place your TFLite model file named **`EfficientNetV2M_OCTDL.tflite`** into `assets/` directory.
   (Alternatively, the app has a "Load .tflite model" button to pick from device at runtime.)
2. From the project root (after unzipping), run:
   ```bash
   flutter pub get
   flutter create .
   ```
   The `flutter create .` step will generate the platform folders (android/ios) needed by Android Studio.
3. Open the project folder in Android Studio: **File → Open** → select `OCT_Detector_App_ver_1.0`.
4. Let Gradle sync. Connect an Android device or start an emulator, then Run the app.
5. Use the "Load .tflite model" button or place the file into `assets/` before building.

## Notes
- The app auto-resizes any selected image to **300×300** to match your model input.
- If your model input size differs, edit `lib/main.dart` constant `inputSize` accordingly.
- If you prefer the app to include the model at build time, put the model in `assets/` and ensure
  `pubspec.yaml` contains the assets entry, then run `flutter pub get` before building.
