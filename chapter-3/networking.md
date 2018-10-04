# Networking

The JavaScript environment that runs in React Native is not like the browser, it's not like Node.js, but it has a little bit of both. One of the gladly convenient APIs available is `fetch`, which allows you to make network requests to servers on the internet.

## Fetch

Just like in the browser, you can call `fetch(url)` and it will return a promise of the response, which you may have to chain with `.then()` call to pick either its textual data or its JSON data. For instance, for textual response:

```js
fetch('https://example.com/name')
  .then(res => res.text())
  .then(text => alert('This is the response text: ' + text));
```

Or for JSON responses:

```js
fetch('https://example.com/data.json')
  .then(res => res.json())
  .then(json => alert(json.field));
```

To practice with `fetch`, you can use the server [jsonplaceholder](https://jsonplaceholder.typicode.com/).

## Read more

[Read more about networking APIs in React Native here](https://facebook.github.io/react-native/docs/network)