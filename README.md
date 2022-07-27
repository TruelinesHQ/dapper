<!-- <img height="300px" src="https://github.com/TruelinesHQ/statex/blob/main/resources/banner.png" alt="Banner" /> -->

<img src="resources/banner.png" alt="Banner" />

<br />

**StateX** is a blazing fast and lightweight library for managing state in a Javascript app.

## Features

- 🛳 **Portable** - This library works accorss web and Node environments. You can use this library together with React or any other Javascript UI libraries.
- 💨 **Fast** − Our APIs just run lightning fast, no more slowdowns.
- 🔋 **Efficient** - To reduce the consumption of energy, we have optimised it.
- 😵 **Tiny (>2kb)** - Too much lightweight, no more large bundle sizes
- 🤓 **Extensible** - Extend the `State` class to create your own custom state object.
- 🫥 **Asynchronous** - If you are fed-up with how messy it is to save state inside a asynchronous operation, say goodbye to it.

## Installation

This will be available when the package is published.

## Documentation

### Simple example

```ts
import { createState, registerEffect } from "statex";

/**
 * Creates a new state object and returns an array of three elements with
 * the first one as the getter and second one as the setter and the third
 * one is the instane of the state object, this might be needed in
 * scenarios when you need to use `registerEffect()` hook.
 *
 * The getter is a function, so you would you have to call it to get the
 * state.
 *
 * The setter is also a function which you need to provide a new value to
 * be passed in to the function. If the new value passed in is the same as
 * the old one is used and the new unchanged value is ignored.
 * This function is type-safe and if the new value's type is not the same
 * as the new one, it will throw an error.
 *
 * The
 */
const [username, setUsername, usernameInstance] = createState("anonymous");

/**
 * Registers an hook to trigger whenever a change is made. If you need to
 * detect changes from the creation of the state, you would need to register
 * it right after creating the state. This means that the changes would only
 * be detected after this hook is registered and not from the beginning.
 * So it would improve perfomance as it would help the developer optimise
 * triggering changes according to their apps.
 *
 * The first parameter is the callback when a new value is triggered. This
 * function also passes in the new value.
 *
 * The second parameter is instance of the state object. You can get the
 * instance from the createState() hook.
 */
registerEffect((newValue) => {
  console.log(newValue);
}, usernameInstance);

// retrieving the value from the state.
console.log(username());

// setting the state, the callback inside the registerEffect() hook
// is triggered
setUsername("hello-world");
```

## License

**StateX** is licensed under `MIT` and the copyright is owned by Haneen Mahdin.
