# Example FlatList

Here's an example of a FlatList that displays all the users from the server, which you can copy-paste into Expo. Note there are two files.

File `App.js`:

```jsx
import React, { Component } from 'react';
import { FlatList, View, StyleSheet } from 'react-native';
import { Constants } from 'expo';
import User from './User';

export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = { users: [] };
  }

  componentDidMount() {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(res => res.json())
      .then(users => {
        this.setState({ users });
      });
  }

  render() {
    return (
      <View style={styles.container}>
        <FlatList
          data={this.state.users}
          renderItem={({ item }) => <User data={item} />}
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

File `User.js`:

```jsx
import React, { Component } from 'react';
import { View, Text, StyleSheet } from 'react-native';

export default class User extends Component {
  render() {
    const { username, email, name, website } = this.props.data;

    return (
      <View style={styles.container}>
        <Text style={styles.name} numberOfLines={1}>
          {username} <Text style={styles.email}>{email}</Text>
        </Text>
        <Text style={styles.detail}>{name}</Text>
        <Text style={styles.detail}>
          {'Website: '}
          {website}
        </Text>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    flexDirection: 'column',
    padding: 10,
    borderBottomWidth: 1,
    borderBottomColor: '#cccccc',
    alignSelf: 'stretch',
    alignItems: 'flex-start',
    justifyContent: 'flex-start',
  },

  name: {
    fontSize: 18,
  },

  email: {
    fontFamily: 'monospace',
    fontSize: 16,
    color: '#999999',
  },

  detail: {
    fontSize: 14,
  },
});
```
