# Example fetch

Here's an example of using `fetch` to get data from a server and display it in the app using `setState`, which you can copy-paste into Expo.

```jsx
import React, { Component } from 'react';
import { View, Text, StyleSheet } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = {};
  }

  componentDidMount() {
    fetch('https://jsonplaceholder.typicode.com/users/1')
      .then(res => res.json())
      .then(json => {
        this.setState(json);
      });
  }

  render() {
    return (
      <View style={styles.container}>
        {this.state.name ? <Text>{this.state.name}</Text> : null}
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
    paddingTop: Constants.statusBarHeight,
    backgroundColor: 'white',
  },
});
```