# Production Command Center — Native Android project

This is an Android Studio source project, **not a compiled APK**. It wraps the existing offline Production Command Center interface in an Android WebView, adds an on-device ZXing barcode scanner, and uses Android's document picker for exporting JSON/CSV/text backups and importing JSON backups. No internet permission or server is used.

## Build an APK
1. Install Android Studio (current stable) and Android SDK Platform 35; use JDK 17.
2. Open the `PCC-Native-Android` folder as a project. Allow Gradle to sync/download dependencies (internet is needed for the **build**, not app use).
3. Choose **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
4. Find the debug APK at `app/build/outputs/apk/debug/app-debug.apk`. Transfer to your Android phone and install after allowing installation from that file manager.
5. Open the app. Data is saved on the phone inside the app's WebView local storage. Export backups regularly from the Backup screen.

## Important limitations
- This is a **native Android container around the web UI**, not a full rewrite into Kotlin screens or a Room database.
- **Do not uninstall or clear app data** without exporting a backup: local records will be lost.
- This app has its own storage sandbox. Data from the old browser-based app is **not automatically migrated**. Export JSON from the old app, then restore that JSON inside this app.
- Android may terminate the app; inspection reminders currently work only while the app is open. They are **not** system notifications.
- There is no authentication, audit trail, validated quality control system, machine connection, or automatic synchronization.
- Use only with employer permission; do not enter controlled or confidential production information without authorization.
- Build has not been verified in this environment (Android SDK and Gradle are not installed here).
