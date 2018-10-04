# Solution

Here's the solution to the exercise, but try to solve it on your own before looking at this!

```jsx
import React, { Component } from 'react';
import { View, Text, TextInput, Button, StyleSheet } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = { words: [] };
    this.inputRef = React.createRef();
    this.inputText = '';
  }

  onPressButton() {
    this.inputRef.value.clear();
    this.setState(prev => ({ words: prev.words.concat(this.inputText) }));
  }

  render() {
    return (
      <View style={styles.container}>
        <View style={styles.row}>
          <TextInput
            ref={this.inputRef}
            onChangeText={text => {
              this.inputText = text;
            }}
            style={styles.input}
            placeholder={'Enter word here'}
          />
          <Button title={'Submit'} onPress={this.onPressButton.bind(this)} />
        </View>
        <Text style={styles.text}>{this.state.words.join(' ')}</Text>
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

  row: {
    flexDirection: 'row',
    alignSelf: 'stretch',
  },

  input: {
    flex: 1,
    height: 40,
    alignSelf: 'stretch',
    fontSize: 20,
  },

  text: {
    marginTop: 20,
    fontSize: 24,
  },
});
```