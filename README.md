# Clear – Android app (Capacitor wrapper)

This folder wraps the Clear web app (`www/index.html`) as a real Android app.
Progress is saved on the phone and survives app restarts.

## One-time setup
1. Install Node.js (LTS) and Android Studio (it includes the Android SDK).
2. In this folder, run:

   npm install
   npm install @capacitor/core @capacitor/android
   npm install -D @capacitor/cli
   npx cap add android

## Build and run
   npx cap sync
   npx cap open android

In Android Studio:
- Test: press Run with a phone plugged in (USB debugging on) or an emulator.
- Share an APK: Build > Build Bundle(s) / APK(s) > Build APK(s).
- Google Play: Build > Generate Signed Bundle / APK > Android App Bundle (.aab).

## Before publishing
- Change `appId` in capacitor.config.json (e.g. com.yourname.clear). It can't change after release.
- Replace the default icon: Android Studio > right-click `res` > New > Image Asset.
- Add a privacy policy URL in Play Console (the app stores data only on-device).

## After you edit the web app
Copy the new HTML into `www/index.html`, then run `npx cap sync` again.
