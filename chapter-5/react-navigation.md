# React Navigation

Finally, the exciting last part of this course: navigation. Most apps have multiple screens linked to each other, and with "back" buttons when they get stacked. The bad news is that React Native [*does not*](https://facebook.github.io/react-native/docs/navigation) come with built-in solutions for this, they actually built something, but it wasn't great. The good news is that the developer community ended up building great libraries for this problem, and we're going to learn the most common one: [React Navigation](https://reactnavigation.org/).

## Install

First, we're going to have to install this library:

```
yarn add react-navigation
```

or:

```
npm install react-navigation
```

## Choose a navigator

There are different ways of handling multiple screens, but the most common are:

- Tabs: at the bottom the user can select which screen they want to see
- Stack: there is only one screen shown at a time, but if you go to another screen, it will be "stacked on top" of the previous one, and you'll see a back button

Let's choose Stack because it's the simplest for now. The library will handle the stacking logic, the back button logic, and will also display a header with title and back button with default styles.

Import `createStackNavigator` from `react-navigation`:

```js
import {createStackNavigator} from 'react-navigation';
```

When we call this function with a configuration object, it will return a "App" component, and that's what we need to use instead of the typical `App` component.

```js
const App = createStackNavigator(configObject);

export default App;
```

Let's learn about the configObject.

## Configure the screens

Each screen will be a React Native component, and will need a name. In this example we will have one home screen (codenamed `Home`) and a details screen (codenamed `Details`).

```js
class HomeScreen extends React.Component {
  // ...
}

class DetailsScreen extends React.Component {
  // ...
}

export default createStackNavigator(
  // THIS IS THE CONFIG OBJECT
  // [codename]: {screen: MyComponent}
  {
    Home: {screen: HomeScreen},
    Details: {screen: DetailsScreen},
  }
);
```

The `createStackNavigator` also allows us to specify which of these screens is the initial one. Let's choose `Home`:

```js
export default createStackNavigator(
  {
    Home: {screen: HomeScreen},
    Details: {screen: DetailsScreen},
  },
  {
    initialRouteName: 'Home',
  },
);
```

## See full example

Open the [next example](./example-react-navigation.md) to see the full code that uses React Navigation.

## Read more

For all things React Navigation, check the [official docs](https://reactnavigation.org) for detailed setup instructions and API explanations.