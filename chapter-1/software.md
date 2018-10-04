# Software

This page describes the software and apps you will have to install to prepare your computer for developing apps with React Native. Try to follow the order given in this page.

### Install Expo on your phone

Install the [Expo app](https://expo.io/tools#client) on your smartphone (either iOS or Android).

### Test that Expo works

- Open [snack.expo.io](https://snack.expo.io) on your computer's browser
- Scan the QR code
  - In the website, press the **Run** button to open a QR code
  - Open Expo app on your smartphone, choose Scan, and aim it at the computer
- **OR** Insert the Device ID
  - In the website, press the **Run** button and select Device ID
  - Open Expo app on your smartphone, and look for the Device ID at the bottom
  - Input the Device ID into the website on your computer
- Check that the example app opens correctly

## Basics in your terminal

We will be using the terminal a lot, so it's important to get familiar with terminals (also known as "console" or "Command Prompt" in Windows). Here's a [quick guide to use `ls` and `cd` in the macOS Terminal](https://www.imore.com/how-use-terminal-mac-when-you-have-no-idea-where-start).

### Setup essentials

**On macOS**: install [Brew](https://brew.sh/) and Chrome (will be used for debugging)

**On Windows**: install Chrome (will be used for debugging) and optionally install [Cmder mini](http://cmder.net/)

**On Linux:** install Chrome (will be used for debugging)

### Install git

**On macOS:**

```
brew install git
```

**On Windows:**

[From the website](https://git-scm.com/downloads).

**On Linux:**

[From the website](https://git-scm.com/download/linux).

### Install nvm

We recommend using [nvm](https://github.com/creationix/nvm) which manages multiple versions of Node.js.

**On macOS or Linux:**

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

**On Windows:**

[From the nvm-windows website](https://github.com/coreybutler/nvm-windows)

### Install Node.js and npm

```
nvm install v8.11
```

```
nvm use v8.11
```

### Install a code editor

We recommend [Visual Studio Code](https://code.visualstudio.com/) which is available for macOS, Windows, and Linux, unless you already have a preferred editor.

### Install React Native tools

Follow these [getting started](https://facebook.github.io/react-native/docs/getting-started) instructions carefully. Choose **Building Projects with Native Code**, choose your **Development OS**, your **Target OS**, and follow the installation instructions.

### Test that you can compile a project

To make sure that all the tools are working correctly for the course, try compiling the demo app (Recipe Explorer).

**Download the project code:**

```
git clone https://github.com/staltz/citw-demo.git
```

**Go into the project folder:**

```
cd citw-demo
```

**Install dependencies:**

```
npm install
```

**Run the Android app:**

Plug the phone to your computer using the USB cable, then run:

```
react-native run-android
```

Or **run the iOS app:**

Plug the iPhone to your Macbook using the USB cable, then run:

```
react-native run-ios
```

If the app shows on your phone with a pink header "Recipe Explorer" and a list of recipes, then you're all set!
