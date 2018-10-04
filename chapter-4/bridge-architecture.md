# Bridge architecture

The way React Native works is complex and mixes multiple technologies, but in the big picture it can be understood as a marionette. There is a JavaScript runtime where you JavaScript code will run, and it is controlling the native parts (Java in the Android case, or ObjectiveC in the iOS case).

When you are developing the project, your JavaScript code will be hosted by a server, called the "React Packager". You can think of this as the same type of software that Webpack. The server can run on your computer, which means your phone will need to communicate with your computer! The computer will run the JavaScript and the phone will run the Java/ObjectiveC. See the diagram below:

```
  +---------------------------+
  |       Your JS code        |
  +---------------------------+
               ^
               |
               v
  +---------------------------+  // This part can run:
  |      React Packager       |  // - On your computer (terminal)
  |      "Metro Bundler"      |
  |       server (8081)       |  // - OR: on your computer (browser)
  +---------------------------+  // - OR: on your phone (for production)
       ^               ^
       |               |
-------|----bridge-----|---------
       |               |
       v               v
  +---------+    +------------+
  |  Java   |    | ObjectiveC |
  | Android |    |    iOS     |
  +---------+    +------------+
```

If your app doesn't work (e.g. it shows a red screen), we will have to double check if all these parts are correctly setup and running.
