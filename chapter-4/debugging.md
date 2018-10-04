# Debugging

To solve issues with your code, you may need to gain more insight into what's going on. The usual `console.log` won't quite work in React Native, but here are your options, in increasing order of sophistication:

- `alert('hello')` works for very simple cases
- `console.warn('hello')` will show a yellow overlay in the corner of the screen
- Use Chrome to debug
  - Shake the phone
  - Choose "Debug JS Remotely"
  - Chrome should open in your computer
  - Open the console and it will show every `console.log` call
  - Breakpoints also work: add `debugger;` in a JavaScript line, and it will make Chrome pause there

## DevTools

If you want to inspect the layout and component tree on the screen, the [React DevTools](https://github.com/facebook/react-devtools/tree/master/packages/react-devtools) work well together with React Native.

## Read more

The official documentation also has [more debugging tips](https://facebook.github.io/react-native/docs/debugging) if you need.