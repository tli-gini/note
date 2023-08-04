### Prior Knowledge

- JS 基礎
- 基本流程控制，if else, for while
- ES6 語法，箭頭 function、.map().forEach 等
- 非同步操作，Promise、Await、Async 等
- Call API、Fetch API 使用等

### Getting Started with React

- cd my-app
- npm start

### React Folders

- node_modules
- public
  - index.html
    - id="root"-- our entire app
- src

### First Component

- Pascal Case:以開頭大寫的方式命名，ex:UserName。

```js
function Greeting() {
  return <h2>My First Component</h2>;
}
```

#### Root Component (only one)

index.js

```js
import React from "react";
import ReactDOM from "react-dom/client";

function Greeting() {
  return <h2>My First Component</h2>;
}

const root = ReactDOM.createRoot(document.getElementById("root"));

root.render(<Greeting />);
//一定要close(</>)
```

#### ES7 Snippets

- rafce (arrow func with export)
- rfce (regular func with export )
- same as the file name
- react auto import
  - uncheck
  - React Snippets › Settings: Import React On Top

rafce

```js
import React from "react";

const App = () => {
  return <div>App</div>;
};

export default App;
```

rfce

```js
import React from "react";

function App() {
  return <div>App</div>;
}

export default App;
```

#### First Component in Detail

- capital letter
- must return something
- JSX syntax (return html)

#### JSX Rules

- return single element (only one parent element)

```js
function App() {
  return (
    <div className="App">
      <h1>react tutorial</h1>
      <p>
        Edit <code>src/App.js</code> and save to reload.
      </p>
    </div>
  );
}
```

- camelCase property naming convention

```js
return (
  <div tabIndex={1}>
    <button onClick={myFunction}>click me</button>
    <label htmlFor='name'>Name</label>
    <input readOnly={true} id='name' />
  </div>
)

// in html
<div tabindex="1">
    <button onclick="myFunction()">click me</button>
    <label for='name'>Name</label>
    <input readonly id='name' />
</div>
```

- className instead of class

```js
return <div className="someValue">hello</div>;
```

- close every element

```js
return <img />;
```

### Nest Components

Before:

```js
function Greeting() {
  return (
    <div>
      <h2>john doe</h2>
      <p>this is my message</p>
    </div>
  );
}
```

After:

```js
function Greeting() {
  return (
    <div>
      <Person />
      <Message />
    </div>
  );
}

const Person = () => <h2>john doe</h2>;
const Message = () => {
  return <p>this is my message</p>;
};
```
