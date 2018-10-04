# Example Flexbox

Here's an example of using Flexbox layout that you can copy-paste into Expo:

```js
import React, { Component } from 'react';
import { View, StyleSheet } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
  render() {
    return (
      <View style={styles.container}>
        <View style={styles.square1} />
        <View style={styles.square2} />
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    flexDirection: 'row',
    alignItems: 'center',
    justifyContent: 'center',
    paddingTop: Constants.statusBarHeight,
    backgroundColor: 'white',
  },

  square1: {
    backgroundColor: 'red',
    flex: 1,
    alignSelf: 'stretch',
  },

  square2: {
    backgroundColor: 'blue',
    flex: 1,
    height: 400,
  },
});
```