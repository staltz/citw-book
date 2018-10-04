# AsyncStorage

Besides controlling the graphical user interface using React components, React Native also comes with built-in APIs to access some of the phone's special capabilities, for instance Geolocation, Clipboard, ImageStore, Vibration, etc. We are only going to learn one of these APIs today, and that's AsyncStorage. But now you know that the other APIs exist, in case you need them.

AsyncStorage provides a simple local database which you can use to store session data, store "bookmarks", and in general any kind of small amount of offline-available data on the phone. You can use it to store information that is only interesting to the user, not to the rest of the world.

## Set

AsyncStorage only supports simple key-value pairs, where both key and value are strings. So, you cannot store objects directly, you have to first convert objects to strings using `JSON.stringify()`. Some examples:

```js
AsyncStorage.setItem('myname', 'Andre');
```

```js
AsyncStorage.setItem('userdata', JSON.stringify({age: 25, name: 'Alice', id: 8175062}));
```

This `setItem` API actually returns a Promise, so if you want to wait for it to complete before doing another action, you must use:

```js
AsyncStorage.setItem(key, value).then(() => {
  // now we are sure that the item was saved in the database
});
```

Or with async-await:

```js
async function myfunction() {
  await AsyncStorage.setItem(key, value);
  // now we are sure that the item was saved in the database
}
```

## Get

To read from the database, provide the key to `getItem` and it will return the a Promise of the value. Remember, the value is a string, so you might need to `JSON.parse` it.

```js
AsyncStorage.getItem('userdata').then(value => {
  const data = JSON.parse(value);
  console.log(data); // {age: 25, name: 'Alice', id: 817062}
});
```

Or with async-await:

```js
async function myfunction() {
  const data = await AsyncStorage.getItem('userdata');
  console.log(data); // {age: 25, name: 'Alice', id: 817062}
}
```

## Read more

Read all about AsyncStorage [in the official docs](https://facebook.github.io/react-native/docs/asyncstorage).
