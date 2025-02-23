---
description: Remède is running on Android. Let's learn how to build Remède for Android !
icon: android
---

# Android development

The Android project is inside `app/android` folder. The following commands need to be executed in the `app` folder.

## Opening Android project

You can open the Android project in Android Studio using :

```shell
ionic capacitor open android
```

## Building for Android

Run the following command and continue in Android Studio where you would build, test and debug the application.

```shell
ionic capacitor build android
```

This command builds the Vue project using `vite` and move the generated resources to the android project, so they can be served through a WebView in the native application.

***

See [Capacitor](https://capacitorjs.com/docs/android) for more information.
