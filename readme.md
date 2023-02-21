<h1 align="center">React Hooks</h1>

<p align="center">

<img src="https://img.shields.io/badge/Made%20by-Ogabek-yellow" >

<img src="https://img.shields.io/badge/bibliothek-js-red">

<img src="https://img.shields.io/badge/react-js-red">

<img src="https://img.shields.io/badge/Learn-React-black">

</p>

<img src="https://fuzeservers.ru/wp-content/uploads/5/9/d/59d7f408f77f60b42c6a8df623455f4d.jpeg">
<center> <h3>What is React Hooks?</h3></center>

>`«Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes.»`

* useState
* useEffect

---

<p align="center" style="font-size:30px;font-weight:900">useState</p>

```jsx
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

>Here, useState is a Hook. We call it inside a function component to add some local state to it. React will preserve this state between re-renders. useState returns a pair: the current state value and a function that lets you update it. You can call this function from an event handler or somewhere else. It’s similar to this.setState in a class, except it doesn’t merge the old and new state together.

>The only argument to useState is the initial state. In the example above, it is 0 because our counter starts from zero. Note that unlike this.state, the state here doesn’t have to be an object — although it can be if you want. The initial state argument is only used during the first render.

---
<p align="center" style="font-size:30px;font-weight:900">useEffect</p>

>`The Effect Hook, useEffect, adds the ability to perform side effects from a function component. It serves the same purpose as componentDidMount, componentDidUpdate, and componentWillUnmount in React classes, but unified into a single API.`

```jsx
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

>When you call useEffect, you’re telling React to run your “effect” function after flushing changes to the DOM. Effects are declared inside the component so they have access to its props and state. By default, React runs the effects after every render — including the first render

>Hooks let you organize side effects in a component by what pieces are related (such as adding and removing a subscription), rather than forcing a split based on lifecycle methods.

---
<p align="center" style="font-size:30px;font-weight:900">✌️ Rules of Hooks</p>

* Hooks are JavaScript functions, but they impose two additional rules:
  * Only call Hooks at the top level. Don’t call Hooks inside loops, conditions, or nested functions.
  * Only call Hooks from React function components. Don’t call Hooks from regular JavaScript functions.

---
