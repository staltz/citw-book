# Styles

Most React Native components have a `style` prop, that allows you to pass an object with properties that customize how the component should look like. For example, here's how you can make a blue square in React Native.

```js
class BlueSquare extends Component {
  render() {
    return <View style={{width: 50, height: 50, backgroundColor: 'blue'}}></View>;
  }
}
```

The properties of the style object are almost always similar to CSS, with the exception that React Native uses camelCase instead of snake-case. For example:

- `background-color` (CSS) becomes `backgroundColor` (React Native)
- `font-size` (CSS) becomes `fontSize` (React Native)

The allowed values are strings and numbers.

See the [style properties allowed by `View`](https://facebook.github.io/react-native/docs/view-style-props) and the [style properties allows by `Text`](https://facebook.github.io/react-native/docs/text-style-props). Be careful not to mix View styles with Text styles, for example, `fontSize` on a View does not work, it works only on Text components.

## Dimensions

Unlike CSS, React Native does not support `width: 50px` nor `width: 50%`. Whenever you need to specify a dimension, you just pass a number, and it will represent a "density-independent pixel".

For most purposes, you don't need to worry about `px` or `%` or `em`, just use a number and it will look approximately the same size on most devices. If you really need to have precise control over the actual pixel dimensions, use the APIs [PixelRatio](https://facebook.github.io/react-native/docs/pixelratio) and [Dimensions](https://facebook.github.io/react-native/docs/dimensions).

## Stylesheets

The `style` prop can be given an object, like below:

```js
class BlueSquare extends Component {
  render() {
    return <View style={{width: 50, height: 50, backgroundColor: 'blue'}}></View>;
  }
}
```

But React Native provides a nicer way, specially when there are many style properties, and that's the `Stylesheet` API. It allows you to create reusable styles that are named, for example:

```js
import {Component} from 'react';
import {Stylesheet, View} from 'react-native';

const styles = StyleSheet.create({
  container: {
    width: 50,
    height: 50,
    backgroundColor: 'blue',
  }
});

class BlueSquare extends Component {
  render() {
    return <View style={styles.container}></View>;
  }
}
```

## Learn more

Learn more about [Styles](https://facebook.github.io/react-native/docs/style), [dimensions](https://facebook.github.io/react-native/docs/height-and-width), [Flexbox](https://facebook.github.io/react-native/docs/flexbox), [View style props](https://facebook.github.io/react-native/docs/view-style-props), and [Text style props](https://facebook.github.io/react-native/docs/text-style-props) in the official documentation.