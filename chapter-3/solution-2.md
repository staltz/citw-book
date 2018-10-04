# Solution

Here's the solution to the exercise, but try to solve it on your own before looking at this!

```jsx
import React, { Component } from 'react';
import { FlatList, View, Image, StyleSheet } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = { photos: [] };
  }

  componentDidMount() {
    fetch('https://jsonplaceholder.typicode.com/photos')
      .then(res => res.json())
      .then(photos => {
        this.setState({ photos });
      });
  }

  render() {
    return (
      <View style={styles.container}>
        <FlatList
          data={this.state.photos}
          renderItem={({ item }) => (
            <Image
              source={{ uri: item.url }}
              style={{ width: 200, height: 200 }}
            />
          )}
        />
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    paddingTop: Constants.statusBarHeight,
    backgroundColor: 'white',
  },
});
```