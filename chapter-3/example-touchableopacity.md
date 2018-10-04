# Example TouchableOpacity

Here's an example of using TouchableOpacity, similar to the previous Button example, which you can copy-paste into Expo.

```jsx
import React, { Component } from 'react';
import { View, Text, TouchableOpacity, StyleSheet } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = { text: '' };
  }

  onPressButton() {
    this.setState(() => ({ text: 'Hello!' }));
  }

  render() {
    return (
      <View style={styles.container}>
        <TouchableOpacity onPress={() => this.onPressButton()}>
          <View style={styles.square} />
        </TouchableOpacity>
        <Text style={styles.text}>{this.state.text}</Text>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    flexDirection: 'column',
    alignItems: 'center',
    justifyContent: 'flex-start',
    margin: 10,
    paddingTop: Constants.statusBarHeight,
    backgroundColor: 'white',
  },

  square: {
    backgroundColor: '#0077ff',
    width: 100,
    height: 100,
    borderRadius: 20,
  },

  text: {
    marginTop: 20,
    fontSize: 24,
  },
});
```