# `<Text>`

The other very common component, besides `View`, is `Text`, which you can think of as similar to `<span>` on the web.

However, unlike the web, textual content can only be inside `Text`, not inside `View`.

```js
// This works :)
<Text>Hello world</Text>
```

```js
// This does NOT work :(
<View>Hello world</View>
```

## Nesting

Text components can be nested, with the special exception that **View inside Text** does not work on Android (but it works on iOS).

```js
// Works everywhere
class TextInANest extends Component {
  render() {
    return (
      <Text>
        <Text>Works</Text> everywhere
      </Text>
    );
  }
}
```

```js
// Works ONLY on iOS
class BlueIsCool extends Component {
  render() {
    return (
      <Text>
        There is a blue square
        <View style={{width: 50, height: 50, backgroundColor: 'steelblue'}} />
        in between my text.
      </Text>
    );
  }
}
```

## Props

Unlike on the web, this Text component has props specific to React Native and mobile apps, to name a few:

- `selectable: boolean`: allows or forbids selecting the textual content (e.g. for copying it to the clipboard)
- `numberOfLines` and `ellipsizeMode`: allow putting a maximum limit on the number of lines for the textual content, and how to display an ellipsis (`...`) when the limit is passed

[Read the API docs for Text here](https://facebook.github.io/react-native/docs/view)
