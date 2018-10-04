# Example Text

Here's an example of nested Text components that you can copy-paste into Expo:

```js
import React, { Component } from 'react';
import { Text, View, StyleSheet } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
  render() {
    return (
      <View style={styles.container}>
        <Text
          style={styles.paragraph}
          numberOfLines={1}
          ellipsizeMode={'middle'}
        >
          Hello <Text style={styles.huge}>crazy weird</Text> world
        </Text>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    paddingTop: Constants.statusBarHeight,
    backgroundColor: '#ecf0f1',
  },

  paragraph: {
    fontSize: 32,
    fontWeight: 'bold',
    textAlign: 'center',
    color: '#34495e',
  },

  huge: {
    margin: 24,
    fontSize: 50,
    fontWeight: 'bold',
    color: '#ff0000',
  },
});
```