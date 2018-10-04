# Project structure

The `react-native init` tool created many folders and files for us. This is the typical project structure for React Native apps, and we shouldn't change it too much (if we want to make it easy to update React Native libraries in the future). The folder structure looks like this:

```
.
├── android
│   ├── app
│   ├── build.gradle
│   ├── gradle
│   ├── gradle.properties
│   ├── gradlew
│   ├── gradlew.bat
│   ├── keystores
│   └── settings.gradle
├── App.js
├── app.json
├── index.js
├── ios
│   ├── MyProject
│   ├── MyProjectTests
│   ├── MyProject-tvOS
│   ├── MyProject-tvOSTests
│   └── MyProject.xcodeproj
├── node_modules
│   └── ...
├── package.json
└── yarn.lock
```

There are a few important parts there.

- `android`: contains Java files and Gradle configs used by Android Studio to compile the Android app
- `ios`: contains ObjectiveC files and Xcode configs used by Xcode to compile the iOS app
- **`App.js`: this is your app's main JavaScript file where you will code**
- `index.js`: this is just an entry JavaScript file, don't edit it unless you know what you're doing
- `package.json`: an npm configuration file where we list the dependencies

There are also many dot files, such as `.babelrc`, `.buckconfig`, `.flowconfig`, `.gitattributes`, `.gitignore`, `.watchmanconfig`. These are important for compiling the app, so keep them.

## Run it

To test if everything is working, connect your phone to the computer with a USB cable, and run this command:

```
react-native run-android
```

or this command:

```
react-native run-ios
```

If it works, congratulations! We can start coding in `App.js`. If it doesn't work, there are many possible reasons. First it's important to learn about the bridge architecture. Once you know about the architecture, it becomes easier to troubleshoot.