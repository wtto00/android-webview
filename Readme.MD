# WebView for Android

Open the Android emulator's WebView using the adb tool in the command line and load the desired URL.

Due to the absence of a `default` image in the `system-images` for Android versions greater than `12.0` 
in the Android emulator, only the `google_apis` image is available. 
The emulator created using `google_apis` has the Chrome browser, 
which may display a protocol popup when opened for the first time, 
blocking the automated process of opening the browser and loading the URL using the adb tool. 
To overcome this, you can install the APK using adb and then use adb to open the app and load the corresponding URL.

## Usage

Install APK using adb
```shell
adb intall --force wang.tato.webview.apk
```

Open the system WebView using adb
```shell
adb shell am start -S -n wang.tato.webview/.MainActivity -d "https://url"
```