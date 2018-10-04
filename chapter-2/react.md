# React

React Native uses [React](https://reactjs.org/), a JavaScript framework for building user interfaces (UIs) on the Web or mobile.

## Components

The center piece of React is the idea of a **component**, which is a reusable piece of UI code. You can think of a component as a tiny slice of the screen.

A component typically looks like this in JavaScript:

```js
import {Component} from 'react';
import {Text} from 'react-native';

class Welcome extends Component {
  render() {
    return <Text>Hello, world</Text>;
  }
}
```

The most important part of a component is the **render** method. It returns a description of how that component should look like on the screen.

## Nesting

Once you have created a React component, you can embed it inside the `render` method of another React component.

```js
class FirstScreen extends Component {
  render() {
    return <Welcome />;
  }
}
```

## Lifecycle

Because components are classes in JavaScript, it initially calls the `constructor`, but there are also more events along the life of a component.

In specific `componentDidMount` is a special method that will be called when the component was just recently inserted into the UI, and `componentWillUnmount` will be called when the component is about to be removed from the UI. You can use these moments to trigger special actions. In the example below, we display popups when the component enters or exits the screen.

```js
class Welcome extends Component {
  componentDidMount() {
    alert('*Welcome* was inserted on the screen');
  }

  componentWillUnmount() {
    alert('*Welcome* will be removed from the screen');
  }

  render() {
    return <Text>Hello, world</Text>;
  }
}
```

## Props

When nested, a child component can take arguments that allow us to customize how the child looks or behaves. These arguments are known as "props" in React jargon. In the example below, we modified `Welcome` so that it displays the name given to it by its parent `FirstScreen`.

```js
import {Component} from 'react';
import {Text} from 'react-native';

class Welcome extends Component {
  render() {
    return <Text>Hello, {this.props.name}</Text>;
  }
}

class FirstScreen extends Component {
  render() {
    return <Welcome name={"Alicia"} />;
  }
}
```

Props also allow the parent component to control how the child component changes over time: if the parent passes a different prop value to the child, then the child will update itself to use the latest prop.

## State

A component can also modify itself internally, by updating its own internal `state`. State is an object in every component, accessible via `this.state` and can be changed with the special method `this.setState(newStateObject)`.

In the example below, we make the Welcome component blink every second by updating a part of the `state`.

```js
class Welcome extends Component {
  constructor(props) {
    super(props); // always needed if you have a constructor
    this.state = {show: true}; // Initialize the state!
  }

  // Once the component is inserted on the screen, begin a timer
  // to toggle the `show` boolean back and forth
  componentDidMount() {
    setInterval(() => {
      this.setState({show: !this.state.show});
    }, 500);
  }

  render() {
    return <Text>{this.state.show ? 'Hello, world' : ''}</Text>;
  }
}
```

Even though the code above works, it's wise to clean up the interval timer in case the Welcome component leaves the UI. We can do that in `componentWillUnmount`.

```js
class Welcome extends Component {
  constructor(props) {
    super(props);
    this.state = {show: true};
  }

  componentDidMount() {
    // Keep a reference to the `interval`
    this.interval = setInterval(() => {
      this.setState({show: !this.state.show});
    }, 500);
  }

  componentWillUnmount() {
    // Clear the `interval`
    clearInterval(this.interval);
  }

  render() {
    return <Text>{this.state.show ? 'Hello, world' : ''}</Text>;
  }
}
```

## Learn more

For more details about React, check the [official docs](https://reactjs.org/), they have a good step-by-step guide there.