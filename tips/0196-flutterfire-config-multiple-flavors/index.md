# FlutterFire Config with Multiple Flavors (Shell Script)

Did you know?

If your Flutter app uses multiple flavors, you can use the FlutterFire CLI to generate the config files for each flavor.

**Pro tip**: create a bash script that takes the flavor as an argument, and run it when needed.

![](196.png)

<!--

If you Flutter app uses multiple flavors, use this command for the Firebase setup

flutterfire config \
  --project=flutter-ship-dev \
  --out=lib/firebase_options_dev.dart \
  --ios-bundle-id=com.codewithandrea.flutterShipApp.dev \
  --ios-out=ios/flavors/dev/GoogleService-Info.plist \
  --android-package-name=com.codewithandrea.flutter_ship_app.dev \
  --android-out=android/app/src/dev/google-services.json

Here’s what all the arguments mean:
--project: The Firebase project to use.
--out: The output path of your Firebase configuration options file.
--ios-bundle-id: The bundle ID of your iOS app.
--ios-out: Where to write the Google-Service-Info.plist file for iOS.
--android-package-name: The package name of your Android app.
--android-out: Where to write the google-services.json file for Android.

Tip: To make life easier, create a script. Then, you can run this once for each flavor:

./flutterfire-config.sh <dev|stg|prod>
-->

Here’s what each argument does:

- `--project`: The Firebase project to use (note: pass the **project ID**, not the alias).
- `--out`: Output path for the Firebase config file.
- `--ios-bundle-id`: iOS app’s bundle ID. Find it in Xcode under **Runner** > **General** > **Identity** > **Bundle Identifier**.
- `--ios-out`: Output path for the iOS `GoogleService-Info.plist`.
- `--android-package-name`: Android app’s package name (found as `applicationId` in `android/app/build.gradle`).
- `--android-out`: Output path for the Android `google-services.json`.

### Pro Tip: Create a Shell Script

To simplify the setup, here's a sample shell script that takes the flavor as an argument:

- [flutterfire-config.sh](https://github.com/bizz84/flutter_ship_app/blob/main/flutterfire-config.sh)

To use this script:

- Copy it to the root of your project
- Update the `project`, `ios-bundle-id`, and `android-package-name` for your app.
- Run it and follow the interactive prompts

---

This is only a small part of the Flutter app flavoring process.

For all the details, check my latest course. 👇

- [Flutter in Production](https://codewithandrea.com/courses/flutter-in-production/)

---

| Previous | Next |
| -------- | ---- |
| [Remote Config via GitHub Gist](../0195-remote-config-github-gist/index.md) | [Dark and Tinted Icons on iOS 18](../0197-dark-tinted-icons-ios-18/index.md) |

<!-- TWITTER|https://x.com/biz84/status/1844285569859453382 -->
<!-- LINKEDIN|https://www.linkedin.com/posts/andreabizzotto_did-you-know-if-your-flutter-app-uses-multiple-activity-7250051558615216129-d14v -->
