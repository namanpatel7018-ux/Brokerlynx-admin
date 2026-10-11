# Brokerlynx (Android APK project)

Contracts, brokerage report, buyer/seller ledgers with GST check, item master, pending deliveries,
and branded PDF contract notes for Sunshine Industries.

## Easiest way to get the APK (no coding, no Android Studio)

1. Create a free account at github.com and click **New repository** (name it `brokerbook`, keep it Private).
2. Click **uploading an existing file**, drag in EVERYTHING from this folder
   (including the hidden `.github` folder), and click **Commit changes**.
   Tip: if hidden folders do not upload by drag and drop, install GitHub Desktop and publish the folder instead.
3. Open the **Actions** tab, choose **Build APK**, then **Run workflow**.
4. After about 5 to 8 minutes, open the finished run and download **BrokerBook-APK** (a zip containing `app-debug.apk`).
5. Send `app-debug.apk` to your phone, tap it, and allow "Install unknown apps" when asked.

## Build on your own computer instead

Needs Node 18+, JDK 17 and Android Studio (for the Android SDK).

    npm install
    npx cap add android
    npx cap sync android
    cd android
    ./gradlew assembleDebug

The APK is at `android/app/build/outputs/apk/debug/app-debug.apk`.

## Notes

- All data is stored on the phone (local storage). It works fully offline.
  Uninstalling the app or clearing its data erases the records.
- PDF buttons open the Android share sheet with the PDF attached. Pick WhatsApp,
  Drive, Gmail or "Save to files".
- To change the company phone, email or footer text, edit the `mk(id)` PDF function in `www/index.html`.
- This is a debug APK, fine for your own devices. A Play Store release needs a signed release build.
