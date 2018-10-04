# TextInput

Where the web has the element `<input type="text">`, React Native has the [`<TextInput>`](https://facebook.github.io/react-native/docs/textinput) component, which allows the user to enter text into the component using the keyboard. Although it has the same purpose as `<input type="text">`, it has different props, methods, and event handlers.

## Value prop

The most important prop is the `value`, allowing you to **set** the textual content of this component. In the example below, the TextInput will **always** have the contents `"Hello"`, even if the user tries to change it with their keyboard.

```jsx
// The TextInput will always be "Hello"!
<TextInput value={"Hello"} />
```

This happens because the TextInput is a [controlled](https://reactjs.org/docs/forms.html) React component, where the `value` prop has absolute control over what the user will see on the screen.

So, instead, we need to handle the user's keyboard events to update the state (with `setState`) and send the state into the `value` prop.

```jsx
<TextInput
  onChangeText={(text) => this.setState({text})}
  value={this.state.text}
  />
```

## Event handlers

The commonly used event handler props on the TextInput are:

- onChangeText: triggered when the user attempts to change the contents
- onFocus: triggered when the component gains focus
- onBlur: triggered when the component loses focus
- onSubmitEditing: triggered when the user presses a special "submit" button on their keyboard

## Other props

Useful and common props on the TextInput include:

- autoFocus: if true, the TextInput will gain focus as soon as it is mounted
- multiline: allows the TextInput wrap the textual content to many lines
- placeholder: a string to display while there is no actual text content

Of course, this above is just a short list of the essentials. For more, [read the API docs for View here](https://facebook.github.io/react-native/docs/textinput)

## More form components

React Native comes with more components for making forms, such as [Switch](https://facebook.github.io/react-native/docs/switch) (a "checkbox"), [Slider](https://facebook.github.io/react-native/docs/slider), and [Picker](https://facebook.github.io/react-native/docs/picker) (a "dropdown list").