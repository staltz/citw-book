# Example state component

Here's an example of a component with dynamic state that you can copy-paste into Expo:

```js
import React, { Component } from 'react';
import { Text, View, StyleSheet } from 'react-native';
import { Constants } from 'expo';

class Countdown extends Component {
  constructor(props) {
    super(props);
    this.state = { count: props.count };
  }

  componentDidMount() {
    this.interval = setInterval(() => {
      this.setState(
        prevState =>
          prevState.count > 0 ? { count: prevState.count - 1 } : prevState,
      );
    }, 1000);
  }

  componentWillUnmount() {
    clearInterval(this.interval);
  }

  render() {
    return (
      <Text style={{ fontSize: 100, color: 'blue', ...this.props.style }}>
        {this.state.count}
      </Text>
    );
  }
}

export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = { toggled: false };
  }

  componentDidMount() {
    setInterval(() => {
      this.setState(prev => ({ toggled: !prev.toggled }));
    }, 3000);
  }

  render() {
    return (
      <View style={styles.container}>
        <Text style={styles.paragraph}>Hello world</Text>
        <Countdown
          count={30}
          style={
            this.state.toggled
              ? { backgroundColor: 'red' }
              : { backgroundColor: 'yellow' }
          }
        />
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
    margin: 24,
    fontSize: 32,
    fontWeight: 'bold',
    textAlign: 'center',
    color: '#34495e',
  },
});

```