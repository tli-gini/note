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

```
