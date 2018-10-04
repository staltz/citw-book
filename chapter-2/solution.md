# Solution

Here's the solution to the exercise, but try to solve it on your own before looking at this!

```jsx
import React, { Component } from 'react';
import { View, Text, StyleSheet } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
  render() {
    return (
      <View style={styles.container}>
        <View style={styles.header}>
          <View style={styles.avatar} />
          <Text style={styles.name}>Firstname lastname</Text>
        </View>
        <View style={styles.body}>
          <View style={styles.square} />
        </View>
        <View style={styles.footer} />
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    flexDirection: 'column',
    alignItems: 'center',
    justifyContent: 'center',
    paddingTop: Constants.statusBarHeight,
    backgroundColor: 'white',
  },

  header: {
    backgroundColor: 'yellow',
    flex: 1,
    flexDirection: 'row',
    alignSelf: 'stretch',
  },

  avatar: {
    backgroundColor: 'blue',
    marginTop: 20,
    marginLeft: 20,
    borderRadius: 10,
    width: 50,
    height: 50,
  },

  name: {
    marginTop: 20,
    marginLeft: 10,
    fontSize: 24,
    color: 'blue',
  },

  body: {
    backgroundColor: 'green',
    flex: 3,
    alignSelf: 'stretch',
    alignItems: 'center',
    justifyContent: 'flex-end',
  },

  square: {
    backgroundColor: 'red',
    width: 100,
    height: 100,
  },

  footer: {
    backgroundColor: 'yellow',
    flex: 1,
    flexDirection: 'row',
    alignSelf: 'stretch',
  },
});
```
