```html
<html>
  <head> </head>
  <body>
    <p id="para1">Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
    <script src="test-for-note.js"></script>
  </body>
</html>
<!--將script置於最後，較不影響DOM運作-->
```

```js
window.addEventListener("load", function () {
  const p1 = document.getElementById("para1");
  console.log(p1);
});

//Output:<p id="para1">Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
```

- Selecting Elements

```js
document.getElementById();
//只能return 一個element
//因為id是獨一無二的

document.getElementsByClassName();
document.getElementsByTagName();
//皆可return 多個elements
```

## HTML DOM (Document Object Model)

- 根據 HTML 標籤，建立的物件結構。
- 每個 HTML 標籤在 JavaScript 引擎中都有對應的標籤物件，即 HTML Element。
- 把 HTML Element 串接在一起，成為物件結構，就是 HTML DOM。

### window 物件操作

- window 物件是 HTML DOM 的入口。
- 隨時可以用內建的 window 變數取得：
  - console.log(window);
- window 物件包含有用的屬性：
  - window.innerWidth //視窗寬度
  - window.ineerHeight //視窗高度
- window 物件包含有用的方法：
  - window.prompt("輸入資料", "預設值")
  - window.alert("彈出警告視窗")

### screen 物件操作

- 內建的 screen 物件紀錄使用者螢幕資訊。
- screen 物件是 window 物件的一個屬性：
  - window.screen
- screen 物件包含有用的屬性：
  - window.screen.width
  - window.screen.height

### document 物件操作

- 內建的 document 物件代表網頁主畫面。
- document 物件是 window 物件的一個屬性：
  - window.document
  - 簡寫：document
- document 物件包含有用的屬性：
  - document.title
  - document.body
- document 物件包含有用的方法：
  - document.querySelector("CSS 選擇器")

## 操作演練

```html
<body>
  <script>
    //1. 認識內建的 window 物件（HTML DOM 的最上層）
    console.log(window);
    //取得視窗寬、高 (會隨視窗滑動改變)
    console.log(window.innerHeight, window.innerWidth);
    console.log(innerHeight, innerWidth);
    //透過 screen 物件，取得螢幕尺寸
    console.log(window.screen.width, window.screen.height);
    //取得網址列的內容
    console.log(window.location.href);
    //更改網址列的內容（跳轉網頁）
    ////window.location.href = "https://www.google.com/";

    //2. 認識 document 物件
    console.log(window.document);
    console.dir(window.document);
    //取得網頁標題
    console.log(document.title);
    //更改網頁標題
    document.title = "新的標題";
    //取得 body 標籤
    console.log(document.body);
    //取得 body 標籤內文
    console.log(document.body.innerHTML);
    //更改網頁主畫面內容（body 標籤內文）
    document.body.innerHTML = "hello world";
  </script>
</body>
```

## 其他標籤物件

- 取得標籤物件
- 操作標籤物件

### 取得標籤物件

- 透過標籤的 ID 屬性建立連結。

1. 在 HTML 想要操作的標籤加上 id 屬性。

```html
<div id="content">這是一段字</div>
<span id="keyword">hello world</span>
```

2. 在 JavaScript 用 document.querySelector() 方法取得標籤物件。

```js
let divElement = document.querySelector("#content");
let spanElement = document.querySelector("#keyword");
```

### 操作標籤物件

- 操作標籤物件的 HTML 屬性和 CSS 設定

1. 取得標籤物件。

```html
<div id="content">這是一段字</div>
<script>
  let divElement = document.querySelector("#content");
</script>
```

2. 操作標籤物件的 HTML 和 CSS。

```html
<div id="content">這是一段字</div>
<script>
  let divElement = document.querySelector("#content");
  divElement.innerHTML = "這是新的字";
  divElement.className = "welcome";
  divElement.style.fontSize = "30px";
  divElement.style.color = "blue";
</script>
```

### 配合使用者點擊

- 使用者點擊後才操作 HTML 標籤
- 在希望被點擊的標籤加上 onclick 屬性

```html
<div id="content">這是一段字</div>
<button onclick="change()">Click</button>
<script>
  function change() {
    let divElm = document.querySelector("#content");
    divElm.innerHTML = "現在換成這行字";
    divElm.style.color = "pink";
  }
</script>
```

### 網頁畫面操作練習

```html
<body>
  <div class="content">
    <span onclick="click1()">關於我</span>
    <span onclick="click2()">學經歷</span>
  </div>
  <hr />
  <div id="text1" style="display: block">大家好，我是 Gini！</div>
  <div id="text2" style="display: none">我畢業於中興大學農藝學系。</div>

  <script>
    function click1() {
      //取得標籤物件
      let aboutMe = document.querySelector("#text1");
      let experience = document.querySelector("#text2");
      //操作標籤物件
      aboutMe.style.display = "block";
      experience.style.display = "none";
    }

    function click2() {
      let aboutMe = document.querySelector("#text1");
      let experience = document.querySelector("#text2");
      aboutMe.style.display = "none";
      experience.style.display = "block";
    }
  </script>
</body>
```
