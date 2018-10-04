# Example remote image

Here's an example of display an image from the internet using the Image component state, which you can copy-paste into Expo.

```jsx
import React, { Component } from 'react';
import { View, Image, StyleSheet } from 'react-native';
import { Constants } from 'expo';

export default class App extends Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <View style={styles.container}>
        <Image
          source={{
            uri:
              'http://i890.photobucket.com/albums/ac107/lebert32/LuLu059.jpg',
          }}
          style={{ width: 300, height: 220 }}
        />
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
});
```
