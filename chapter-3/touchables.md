# Touchables

The other kind of common user interaction in mobile apps, besides text input, is handling presses. React Native makes it possible to make any component handle user touches, using `Touchable*` components. They come in different flavors:

- [TouchableOpacity](https://facebook.github.io/react-native/docs/touchableopacity)
- [TouchableHighlight](https://facebook.github.io/react-native/docs/touchablehighlight)
- [TouchableNativeFeedback](https://facebook.github.io/react-native/docs/touchablenativefeedback)
- [TouchableWithoutFeedback](https://facebook.github.io/react-native/docs/touchablewithoutfeedback)

But they all work the same way. These are **wrapper** components. They are not useful by themselves but they exist so you can put them around some existing component, for instance any `<View>`.

```js
<TouchableOpacity onPress={() => alert('View was pressed!')}>
  <View style={styles.blueSquare} />
</TouchableOpacity>
```

All these Touchable variants have the `onPress` prop. The variants differ by how they look like when the user touches them:

- TouchableOpacity: when pressed, will make the child component slightly more transparent
- TouchableHighlight: like TouchableOpacity, but has an underlay color
- TouchableNativeFeedback (only on Android): when pressed, displays a ripple effect
- TouchableWithoutFeedback: when pressed, looks the same as when not pressed

## Button

With Touchables, you can create your own button with a custom look-and-feel. However, if you want to just make a button that looks like standard iOS buttons or standard Android buttons, use the simple `<Button>` component, that has props:

- onPress: the event handler function
- title: the textual content in the button
- color: (on Android:) the background color for the button, or (on iOS:) the color of the text

[Read the API docs for Button here](https://facebook.github.io/react-native/docs/button)
