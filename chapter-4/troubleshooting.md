# Troubleshooting

## "Could not connect to development server"

If the app opens with a red screen saying that it couldn't find the app bundle, then it could be for one of these reasons:

- The server is not running on your computer yet
- The phone is not in the same Wi-Fi network as the computer is
- The phone does not know the correct IP address for the computer

So first make sure that the React packager server is running on your computer. It usually runs on port 8081, so you need to check if it's running, e.g. run the command `lsof -i :8081`. If lsof returns nothing, then there is no packager server.

To run the packager server, run `npm start`, and you should see this in the terminal:

```
┌────────────────────────────────────────────────────────────────────────────┐
│                                                                              │
│  Running Metro Bundler on port 8081.                                         │
│                                                                              │
│  Keep Metro running while developing on any JS projects. Feel free to        │
│  close this tab and run your own Metro instance if you prefer.               │
│                                                                              │
│  https://github.com/facebook/react-native                                    │
│                                                                              │
└────────────────────────────────────────────────────────────────────────────┘
```

Then, make sure both phone and computer are on the same network, and:

- Discover your computer's IP address with `ifconfig` (macOS) or `ip addr` (Linux)
- Shake your phone (really, shake it!) until a menu shows
- Choose "Dev Settings", then choose "Debug server host & port for device" and insert your computer's IP address and port, for example `192.168.1.115:8081`
- Go back, and re-shake your phone, then choose "Reload"

## Read more

The official documentation also has [more troubleshooting instructions](https://facebook.github.io/react-native/docs/troubleshooting) if you need.
