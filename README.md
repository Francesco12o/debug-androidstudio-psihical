
# debug-androidstudio-psihical

Tools and instructions for debugging an Android Studio project on a physical Android device.

## Requirements
- Android Studio installed  
- USB debugging enabled on the phone  
- Android Platform Tools in PATH  

## Android Studio Setup
1. Open Android Studio.  
2. Open the project folder `debug-androidstudio-psihical`.  
3. Wait for Gradle to finish syncing.  
4. Connect the physical device with USB debugging enabled.  
5. Look at the device selector in the top toolbar. The physical device should appear.  
6. Select the device.  
7. Choose the "Debug" configuration.  
8. Press the Run or Debug button to install and launch the app on the device.  
9. Use **Logcat** at the bottom panel to inspect real-time logs.  
10. If the device does not show up, ensure proper USB drivers are installed or restart ADB.

## CLI Workflow
- Check connection: `adb devices`  
- Build debug version: `./gradlew assembleDebug`  
- Install APK: `adb install -r app/build/outputs/apk/debug/app-debug.apk`  
- Show logs: `adb logcat`  

## Project Structure
- `app/` Android app source  
- `gradle/` build rules  
- `scripts/` optional automation  

## Troubleshooting
- Restart ADB: `adb kill-server` then `adb start-server`  
- Reconnect USB cable if Android Studio does not detect the device  
- Confirm USB mode is set to "File Transfer" on the device
