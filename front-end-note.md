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

## 解構賦值 ( )

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

3. 變數資料交換

```js
let n1 = 3,
  n2 = 4;
[n2, n1] = [n1, n2];
console.log(n1, n2);
//4 3
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

4. 統整函式的物件參數

```js
function add(args) {
  console.log(args.n1 + args.n2);
}
add({ n1: 3, n2: 4 });
// 7
```

```js
function plus({ m1, m2 }) {
  console.log(m1 + m2);
}
plus({ m1: 3, m2: 4 });
// 7
```

## 其餘運算符號 (Rest Operator)

- 顧名思義，把剩餘的東西包在一起。
- 運算符號，三個點 ...
- 運用在解構賦值：
  - 陣列：把剩餘的資料包在一個新陣列。
  - 物件：把剩餘的成員包在一個新物件。
- 運用在函式參數：
  - 把剩餘的參數包在一個新陣列。

### ... - 陣列解構賦值

- 未逐一指定名稱的剩餘值，運用其餘運算符號，包在新陣列中。
- 陣列解構賦值的運用：

```js
let arr = [3, 4, 5, 6, 2];
let [d1, d2, ...data] = arr;
console.log(data);
// [5,6,2]
```

- 限制：必須放最後面

```js
let arr = [3, 4, 5, 6, 2];
let [d1, ...data, d2] = arr;
// error
```

### ... - 物件解構賦值

- 未逐一指定名稱的剩餘值，運用其餘運算符號，包在新物件中。
- 物件解構賦值的運用：

```js
let obj = { x: 3, y: 4, z: 5 };
let { x, ...data } = obj;
console.log(data);
// {y:4, z:5}
```

- 限制：必須放最後面

```js
et obj = { x: 3, y: 4, z: 5 };
let { ...data, x } = obj;
// error
```

### 其餘參數 (Rest Parameter)

- 未逐一指定參數名稱的參數資料，運用其餘運算符號，包在陣列中。
- 其餘參數的運用：

```js
function test(a, b, ...data) {
  console.log(a, b);
  // 3 4
  console.log(data);
  // [1, 2, 5]
}
test(3, 4, 1, 2, 5);
```

- 限制：必須放最後面

```js
function test(a, ...data, b) {
  // error
  console.log(a, b);
  console.log(data);
}
```

- 範例：

```js
function add(n1, n2, ...args) {
  //其餘參數 Rest Parameter
  console.log(n1, n2, args);
  let total = n1 + n2;
  for (let i = 0; i < args.length; i++) {
    total = total + args[i];
  }
  console.log(total);
  // 7
  // 14
  // 8
}
add(3, 4); // 3 4 []
add(5, 6, 1, 2); // 5 6 [1, 2]
add(1, 2, 3, 1, 1); // 1 2 [3, 1, 1]
```

## 模組 Modules

- 單一程式切割為多個檔案，每個檔案稱之為模組。
- 早期的前端 JavaScript 沒有良好的模組支援，可使用 Webpack 解決。
- 現代的前端 JavaScript 擁有完整的模組能力，支援獨立的模組名稱空間，以及 export / import 語法。

#### 假設有一個很大的程式

```js
function echo(msg) {
  console.log(msg);
}
let message = "很大的程式";
echo(message);
```

#### 想要切割為兩個檔案

- 使用 JavaScript 模組系統

1. 檔案名稱：lib.js

```js
function echo(msg) {
  console.log(msg);
}
```

2. 檔案名稱：main.js

```js
let message = "很大的程式";
echo(message);
```

3. HTML 中引入主要的程式檔案

```html
<script type="module" src="main.js"></script>
```

- 錯誤：不同檔案沒有互通，無法呼叫函式

### 建立輸出輸入的關聯性

- 使用 export 語法輸出資料
- 使用 import 語法輸入資料

1. 檔案名稱：lib.js

```js
function echo(msg) {
  console.log(msg);
}

export default echo;
// export default 資料
```

2. 檔案名稱：main.js

```js
import echo from "./lib.js";
// import 資料 from "模組檔案路徑"

let message = "很大的程式";
echo(message);
```

3. HTML 中引入主要的程式檔案

不變

```html
<script type="module" src="main.js"></script>
```

### 模組的獨立性

- 模組有各自的名稱空間，互不影響。

1. 檔案名稱：lib.js

```js
function echo(msg) {
  console.log(msg);
}
let message = "Hello World";
echo(message);

export default echo;
```

2. 檔案名稱：main.js

```js
import echo from "./lib.js";

let message = "很大的程式";
echo(message);
```

## 原型鏈 Prototype Chain

### 取得原型物件：

- Object.getPrototypeOf(物件)

```js
// 定義一個類別
class Car {
  constructor(color) {
    this.color = color;
  }
  run() {}
}

// 產生類別物件
let car = new Car("green");

// 取得並將原型物件顯示出來
let carProto = Object.getPrototypeOf(car); // Car 原型物件
console.log(carProto);
let objProto = Object.getPrototypeOf(carProto); // Object 原型物件
console.log(objProto);
let lastOne = Object.getPrototypeOf(objProto); // 原型鏈的終點：null
console.log(lastOne);
```

### 繼承關係中的原型鏈：

```js
// 定義一個類別
class Car {
  constructor(color) {
    this.color = color;
  }
  run() {}
}

// 定義子類別
class ElectricCar extends Car {
  constructor(color) {
    super(color);
    this.battery = 100;
  }
  run(distance) {}
  charge() {}
}

// 產生子類別物件
let car = new ElectricCar("green");
car.run(); // how to work?
```

### 在物件實體上，直接定義屬性或方法

```js
// 定義一個類別
class Car {
  constructor(color) {
    this.color = color;
  }
  run() {}
}

// 定義子類別
class ElectricCar extends Car {
  constructor(color) {
    super(color);
    this.battery = 100;
  }
  run(distance) {}
  charge() {}
}

// 產生子類別物件
let car = new ElectricCar("green");
// 在物件實體直接建立方法或屬性
car.name = "toyota";
car.test = function () {
  console.log("建立物件後，在物件實體上新增方法");
  console.log(this.name); // Output: toyota
};
car.test();
```

## 定義、呼叫靜態方法 Static

### 靜態方法：與類別綁定的方法

- 在類別中，定義靜態方法

```js
static 方法名稱(參數){內部程式碼}
```

- 呼叫靜態方法

```js
類別名稱.方法名稱(參數);
```

- 靜態方法和類別綁定
- 其他方法或屬性和物件實體綁定

```js
class Car {
  constructor(color) {
    this.color = color;
  }
  run() {
    console.log("Color " + this.color + " Running");
  }
  static showColors() {
    // 定義一個靜態方法
    console.log("We support three colors: blue, red, green.");
  }
}

// 直接使用類別名稱，呼叫靜態方法
Car.showColors();
Car.run(); // Uncaught TypeError: Car.run is not a function
// run 非靜態方法，必須由物件實體呼叫

// 產生新物件實體
let carObj = new Car("blue");
carObj.run(); // 使用物件實體，呼叫物件的方法 run();
carObj.showColors(); // Uncaught TypeError: carObj.showColors is not a function
// showColors 為靜態方法，必須由類別名稱呼叫
```
