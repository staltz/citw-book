# Image

Where the web has the element `<img src="cat.jpeg">`, React Native has the [`<Image>`](https://facebook.github.io/react-native/docs/image) component. There are several differences between these two, worth highlighting.

The most visible difference is that in React Native the prop is `source`, not `src`. And the value for this prop is not a URL, it's usually an object:

```js
<Image
  style={{width: 300, height: 200}}
  source={{uri: 'https://placekitten.com/408/287'}}
  />
```

Note the difference:

- `src="https://placekitten.com/408/287"` (HTML)
- `source={ {uri: 'https://placekitten.com/408/287'} }` (React Native)

## Always fixed size

Unlike on the web, images in React Native **do not resize to fit the image content** after it is fetched. You must specify the size of the image before it is fetched. You can either do this with fixed numbers for `width` and `height`:

```js
<Image
  style={{width: 300, height: 200}}
  source={{uri: 'https://placekitten.com/408/287'}}
  />
```

Or one of these can stretch to 100%, using Flexbox `alignSelf`:

```js
// Suppose the parent component has `flexDirection: 'column'`
<Image
  style={{alignSelf: 'stretch', height: 200}}
  source={{uri: 'https://placekitten.com/408/287'}}
  />
```

Or:

```js
// Suppose the parent component has `flexDirection: 'row'`
<Image
  style={{width: 300, alignSelf: 'stretch'}}
  source={{uri: 'https://placekitten.com/408/287'}}
  />
```

## Local images

Besides images from the internet, you can also display local images from your project's folder, just "require" the file and pass it as the `source` prop:

```js
<Image source={require('./my-icon.png')} />
```

## Read more

[Read a guide to using images here](https://facebook.github.io/react-native/docs/images).

[Read the API docs for the Image component here](https://facebook.github.io/react-native/docs/image).