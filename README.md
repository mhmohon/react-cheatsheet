<div align="center">
  <h1>React Cheatsheets</h1>
</div>

### Table of Contents

<summary><b>Expand Table of Contents</b></summary>

- [Section 1: Initial Setup](#section-1-setup-typescript-with-react)
  - [Prerequisites](#prerequisites)
  - [Import React](#import-react)
- [Section 2: Getting Started](#section-2-getting-started)
  - [Function Components](#function-components)
  - [Hooks](#hooks)
  - [useState](#usestate)
  - [useReducer](#usereducer)
  - [useEffect](#useeffect)
  - [useRef](#useref)
  - [useImperativeHandle](#useimperativehandle)
  - [Custom Hooks](#custom-hooks)

  <!--START-SECTION:setup-->

# Section 1: Setup React

## VS Code Extensions

- refactoring help https://marketplace.visualstudio.com/items?itemName=paulshen.paul-typescript-toolkit
- R+TS Code Snippets (there are a few...)
  - https://marketplace.visualstudio.com/items?itemName=infeng.vscode-react-typescript
  - https://www.digitalocean.com/community/tutorials/the-best-react-extension-for-vs-code
- TypeScript official extension https://code.visualstudio.com/docs/languages/typescript

<!--END-SECTION:setup-->

<!--START-SECTION:hooks-->

## Hooks

Hooks are [supported in `@types/react` from v16.8 up](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/a05cc538a42243c632f054e42eab483ebf1560ab/types/react/index.d.ts#L800-L1031).

## useState

Type inference works very well for simple values:

```js
const [count, setCount] = useState(initialCount);
// `count` is inferred to be variable name
// `setCount` a function is used to update the count
// `initialCount` initial value
```

Example:
```js
import React, { useState } from 'react';

function Example() {
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
> Never modify the state manually.
## useEffect / useLayoutEffect

By default, React runs the effects after every render — including the first render
```js
  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  }, [count]);
  // `[]` dependency array for the trigger useEffect function. If it is empty then it will load only initalComponent load.
  // `[count]` the trigger variable names. useEffect will call each time those value will changed.
```
Example:
```js
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);
  
  useEffect(() => {
    document.title = `You clicked ${count} times`;
  }, [count]);
 
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
<!--END-SECTION:hooks-->
## Contributors

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. See [CONTRIBUTORS.md](/CONTRIBUTORS.md) for the full list. Contributions of any kind welcome!
