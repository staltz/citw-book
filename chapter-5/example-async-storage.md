# Example – AsyncStorage

This example is the same as the TextInput exercise from Tuesday with a submit button , except we use AsyncStorage to save the submitted data in the local database with AsyncStorage, so it persists after the app is closed.

```js
import React, { Component } from 'react';
import {
  View,
  Text,
  TextInput,
  Button,
  AsyncStorage,
  StyleSheet,
} from 'react-native';

export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = { words: [] };
    this.inputRef = React.createRef();
    this.inputText = '';
  }

  componentDidMount() {
    AsyncStorage.getItem('words').then(words => {
      if (words) {
        this.setState({ words: JSON.parse(words) });
      }
    });
  }

  onPressButton() {
    this.inputRef.value.clear();
    this.setState(prev => {
      const words = prev.words.concat(this.inputText);
      AsyncStorage.setItem('words', JSON.stringify(words));
      return { words };
    });
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
    paddingTop: 24,
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