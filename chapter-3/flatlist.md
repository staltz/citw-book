# FlatList

One of the most common user experiences on mobile is "infinite scrolling" of a very large amount of data. It is unwise to download and display all of that data at once, because it might be too much for the phone to handle and compute.

So instead, we need a way of gradually fetching and gradually displaying new content, dynamically as the user is scrolling. This is a very challenging problem to solve, but gladly there is a built-in React Native component dedicated to just that, called **FlatList**.

## renderItem

While ScrollView allows you to insert many children, FlatList does not have any children. Instead, you pass it an array of data in the prop called `data`, and then a prop called `renderItem` takes a function that knows how render a single item in that list. For this reason, FlatList is suitable when all the items in the list are of the same type.

```js
<FlatList
  data={['Alice', 'Bob', 'Carla', 'David', 'Eve', 'Fred', 'Gloria']}
  renderItem={({ item }) => <Text>item</Text>}
  />
```

Note that the prop `renderItem` needs a function. This function should look like this:

- Input: an object `{item, index, ...etc}` which is provided to you
- Output: a React element, e.g. `<Text>` or `<View>` or `<MyComponent>`

## keyExtractor

Because FlatList doesn't show all the items in the `data` array at the same time, and because the user is scrolling (maybe even scrolling very fast!), FlatList needs to have a way of detecting the true identity of each item. For this reason, you may have to provide the `keyExtractor` prop with a function:

```js
<FlatList
  data={[{id: 28, name: 'Alice'}, {id: 12, name: 'Bob'}]}
  keyExtractor={(item, index) => item.id}
  renderItem={({ item }) => <Text>item.name</Text>}
  />
```

## Other props

FlatList is actually a special type of ScrollView, so it supports all the props that ScrollView supports, but more! It allows advanced customization, such as:

- ListHeaderComponent: customize the header of the FlatList
- ListFooterComponent: customize the footer of the FlatList
- ItemSeparatorComponent: specify a component that is rendered between every two items
- onEndReached: event handler that is triggered when the user has scrolled to the bottom, this is usually a good place where to request more data and increase the size of the array

## Read more

[Read the API docs for FlatList here](https://facebook.github.io/react-native/docs/flatlist)
