---
title: "The Road To React"
date: 2021-05-11T14:05:40+09:00
draft: false
tags: 
  - REACT
  - FRONT-END
categories: 
  - IT
---

**TODO**:

- [ ] page 25. Consider how we can include a React application in an external web application that uses HTML.

### Hoisting

1. Before the declaration of the function or variables, you can use them.
2. Only declarations are hoisted, without **initialize**.
3. Initializations using **let** and **const** are also not hoisted.

```js
// The program can be excuted without any errors.
console.log(num); //output undefined 
num = 7;
var num;
```

### Scoping

1. **let** and **const** are block-scoped in JS, in contrast to **var**, which is function-scoped.

### Const vs Let

1. A variable declared with **const** cannot be re-assigned.
2. A variable declared with **let** can be re-assigned.
3. :metal: If **const** is used for a JavaScript object or array, its internal properties **can** still be re-assigned.
  
### Arrow Function

#### Syntax

##### Basic syntax

- One param. With simple expression return is not needed:

```js
param => expression
```

- Multiple params require parentheses. With simple expression return is not needed:

```js
(param1, paramN) => expression
```

- Multiline statements require body brackets and return:

```js
param => {
  let a = 1;
  return a + param;
}
```

- Multiple params require parentheses. Multiline statements require body brackets and return:

```js
(param1, paramN) => {
   let a = 1;
   return a + param1 + paramN;
}
```

##### Advanced syntax

- To return an object literal expression requires parentheses around expression:

```js
params => ({foo: "a"}) // returning the object {foo: "a"}
```

- Rest parameters are supported:

```js
(a, b, ...r) => expression
```

- Default parameters are supported:

```js
(a=400, b=20, c) => expression
```

- Destructuring within params supported:

```js
([a, b] = [10, 20]) => a + b;  // result is 30
({ a, b } = { a: 10, b: 20 }) => a + b; // result is 30
```

### React jsx

- [Official Doc](https://zh-hans.reactjs.org/docs/introducing-jsx.html)
- Array.prototype.reduce() [link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

> The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

- [SyntheticEvent](https://reactjs.org/docs/events.html#gatsby-focus-wrapper)

### UNCONTROLLED VS. CONTROLLED COMPONENT

[link](https://www.robinwieruch.de/react-controlled-components)

1. Uncontrolled Component

  ```jsx
  import React, { useState } from 'react';
 
  const App = () => {
    const [value, setValue] = useState('Hello React');
    
      const handleChange = event => setValue(event.target.value);
    
      return (
        <div>
          <label>
            My still uncontrolled Input:
            <input type="text" onChange={handleChange} />
          </label>
    
          <p>
            <strong>Output:</strong> {value}
          </p>
        </div>
      );
    };
    export default App;
  ```

- **input** field receives its value from internal DOM node state
- **output** paragraph receives its value from React's state

2. Controlled Component. By giving the input the value from React's state, it doesn't use anymore its internal state, but the state you provided from React.

```jsx
import React, { useState } from 'react';
 
const App = () => {
  const [value, setValue] = useState('Hello React');
 
  const handleChange = event => setValue(event.target.value);
 
  return (
    <div>
      <label>
        My controlled Input:
        <input type="text" value={value} onChange={handleChange} />
      </label>
 
      <p>
        <strong>Output:</strong> {value}
      </p>
    </div>
  );
};
 
export default App;
```

### Destructuring assignment

```js
// Syntax

let a, b, rest;
[a, b] = [10, 20];
console.log(a); // 10
console.log(b); // 20

[a, b, ...rest] = [10, 20, 30, 40, 50];
console.log(a); // 10
console.log(b); // 20
console.log(rest); // [30, 40, 50]

({ a, b } = { a: 10, b: 20 });
console.log(a); // 10
console.log(b); // 20

// Stage 4(finished) proposal
({a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40});
console.log(a); // 10
console.log(b); // 20
console.log(rest); // {c: 30, d: 40}
```
