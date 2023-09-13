## HTTP 通訊協定

### 網址 Web Address (URL)

- 不同網址，代表網路上不同的服務或資源。
- 網站服務就是由各式各樣的網址組成的綜合呈現。

### 網址組成

- 通訊協定://主機名稱/路徑
  - 通訊協定 (Protocol)
  - 主機名稱 (Hostname)
  - 路徑 (Path)

### 網站前後端互動基礎

- 透過網址，前端可以連線取得後端資源。
- 實際情境：
  - 在瀏覽器網址列上輸入網址，按下 Enter 取得網頁。
  - 可以採用 AJAX / XHR 技術執行網址連線、取資料的動作。

## AJAX 網路連線實務

### AJAX / XHR 技術簡介

- 利用 JavaScript 程式進行網路連線。
  - 初期稱作 Asynchronous JavaScript And XML 技術。
  - 中期使用 XMLHttpRequest 物件，稱為 XHR 技術。
  - 近年，建議採用最新的 fetch 函式來執行網路連線功能。

## 使用 fetch 實作 AJAX 技術

### 網路連線的步驟

- 了解網址和 HTTP 通訊協定的運作。
  1. 確認要連線的網址是什麼
  2. 建立、發出連線
  3. 取得伺服器的回應

### 使用 fetch 函式

- JavaScript 內建的連線用函式
- 基本語法詳解：

```js
fetch(網址).then(function (回應物件) {
  console.log(回應物件);
});
```

### 處理不同格式的回應

- 根據網址連線後的回應，寫出對應的程式。
- 取得純文字的回應：

```js
fetch(網址)
  .then(function (response) {
    return response.text();
  })
  .then(function (data) {
    console.log(data);
    //純文字資料
  });
```

- 取得 JSON 格式的回應：

```js
fetch(網址)
  .then(function (response) {
    return response.json();
  })
  .then(function (data) {
    console.log(data);
    //JSON 格式 資料
  });
```

### 測試網址

https://cwpeng.github.io/live-records-samples/data/products.json

## 解構賦值 (Destructuring Assignment)

- 解構：把陣列或物件中的資料拆開。
- 賦值：將拆開的資料分別放入個別的變數中。

### 陣列解構賦值：基本操作

- 將陣列中的資料分開賦值給變數，按順序做對應。

- 傳統做法：

```js
let arr = [3, 4, 5];
let d1 = arr[0];
let d2 = arr[1];
let d3 = arr[2];
```

- 解構賦值語法

```js
let arr = [3, 4, 5];
let [d1, d2, d3] = arr;
```

### 各種變形

- 陣列解構賦值的變形寫法：

1. 宣告與賦值分開

```js
let arr = [3, 4, 5];
let d1, d2, d3;
[d1, d2, d3] = arr;
```

2. 預設值

```js
let arr = [3, 4];
let d1, d2, d3;
[d1, d2 = 2, d3 = 5] = arr;
```

### 物件解構賦值：基本操作

- 將物件中的資料分開賦值給變數，按物件成員名稱做對應。

- 傳統做法：

```js
let obj = { x: 3, y: 4 };
let x = obj.x;
let y = obj.y;
```

- 解構賦值語法

```js
let obj = { x: 3, y: 4 };
let { x, y } = obj;
```

### 各種變形

- 物件解構賦值的變形寫法：

1. 宣告與賦值分開

```js
let obj = { x: 3, y: 4 };
let x, y;
({ x, y } = obj); //注意：不和宣告一起執行，要多加()
```

2. 預設值

```js
let obj = { x: 3 };
let x, y;
({ x, y = 5 } = obj);
```

3. 指定新的變數名稱

```js
let obj = { x: 3, y: 4 };
let newX, newY;
({ x: newX, y: newY } = obj);
```
