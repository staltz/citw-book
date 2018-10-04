# ScrollView

Sometimes your components don't fit all in the same screen, and they may overflow the max height. On the web, this would automatically create the possibility to scroll. On React Native, we need to do this ourselves, by wrapping our components with a `<ScrollView>` parent.

```jsx
<ScrollView>
  <Text>Lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>and lots and lots</Text>
  <Text>of text that goes beyond</Text>
  <Text>the maximum height</Text>
  <Text>of the phone's screen</Text>
</ScrollView>
```

That said, unlike on the web, ScrollView comes with many props to customize the scrolling experience: does it snap to a grid or is it fluid? Does it bounce when it reach the ends? Does the keyboard hide when we are scrolling? How does the deceleration feel like to the user? On mobile, scrolling is one of the core user experiences, so ScrollView allows controlling this user experience in details.

## Read more

[Read the API docs for ScrollView here](https://facebook.github.io/react-native/docs/scrollview)
