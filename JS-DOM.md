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
