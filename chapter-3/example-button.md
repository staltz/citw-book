# Example Button

Here's an example of using Button to change component state, which you can copy-paste into Expo.

```jsx
import React, { Component } from 'react';
import { View, Text, Button, StyleSheet } from 'react-native';
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
        <Button onPress={() => this.onPressButton()} title={'Press me'} />
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

  text: {
    marginTop: 20,
    fontSize: 24,
  },
});
```