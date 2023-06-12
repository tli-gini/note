# 基本變數

```js
let myName = "註冊成功";
//let 容器=“內容物”
//"let":宣告(告訴電腦)
//"=":將右邊的東西丟給左邊
console.log(myName); //Output:註冊成功
```

```js
let myName = "Gini"; //string 字串
let score = 10; //number(可用小數點)
let isFake = true; //boolean
let bag1 = undefined;
let bag2 = null;
//undefined 不等於 null
```

- string

```js
let myName = "Gini";
let myAge = "今年24歲";
let aboutMe = myName + myAge;
console.log(aboutMe);
//Output:Gini今年24歲
```

- number

```js
let score = 100;
//+ - * / %
console.log(score + 50);
//Output:150
console.log(score % 3);
//Output:1
```

- let、var、const

  - let 可取代 var

- let v.s. const

```js
let a1 = "aaa";
console.log(a1);
//修改a1內容
a1 = "bbb";
console.log(a1);
//Output:bbb

const a1 = "aaa";
console.log(a1);
//const設定a1是常數，內容無法改變
a1 = "bbb";
console.log(a1);
//Error
```

# 陣列（Array）、物件（Object）

- Array

```js
let ClassA = ["小新", "風間", "妮妮"];
console.log(ClassA);
//Output:(3) ['小新', '風間', '妮妮']
ClassA.push("阿呆");
console.log("轉學後:", ClassA);
//Output:(4) ['小新', '風間', '妮妮', '阿呆']
console.log(ClassA.length);
//Output:4

//可以應用於放很多圖片等
let IgPhoto = [
  "https://fakeimg.pl/600x400",
  "https://fakeimg.pl/300x300",
  "https://fakeimg.pl/100x100",
];
console.log("第一張", IgPhoto[0]);
console.log("第二張", IgPhoto[1]);
```

- Object

```js
const Card = {
  name: "Gini",
  address: "台灣台北市",
  phone: 0912345678,
};
console.log("名字：", Card.name);
//Output:名字： Gini
//. =>Card的name

const Post1 = {
  img: "https://fakeimg.pl/600x400",
  content: "Hello World 1",
  date: "2023 / 05 / 24",
  comment: ["Wow!1", "Cool!1", "Good!1", "Nice!1"],
};

const Post2 = {
  img: "https://fakeimg.pl/300x300",
  content: "Hello World 2",
  date: "2023 / 05 / 25",
  comment: ["Wow!2", "Cool!2", "Good!2", "Nice!2"],
};

const Wall = [Post1, Post2];
console.log(Wall);
```

# 流程控制：if else, switch case

- 邏輯運算子：&&, ||, !

```js
//&& 兩邊都是true, 結果才是true
//|| 只要有一邊是true, 結果就是true
//! 結果相反

let condition1 = true && false;
console.log(condition1);
//Output:false

let condition2 = !(true && false);
console.log(condition2);
//Output:true

let condition3 = true || false;
console.log(condition3);
//Output:true

let condition4 = !(true || false);
console.log(condition4);
//Output:false
```

- if else

```js
if(/*條件*/){
    //條件成立要做的事(true)
}else{
    //條件不成立要做的事(false)
}
```

```js
if (10 > 50) {
  console.log("成立");
} else {
  console.log("錯誤");
}
//Output:錯誤
```

```js
let score = 70;

if (score >= 100) {
  console.log("Great!");
} else if (score >= 75) {
  console.log("OK!");
} else if (score >= 60) {
  console.log("Try Harder!");
} else {
  console.log("Fail.");
}
//Output:Try Harder!
```

- switch case

```js
let key = 1000;
switch (key) {
  case 100:
    console.log("100分");
    break;
  case 200:
    console.log("200分");
    break;
  case 300:
    console.log("300分");
    break;
  default: //沒有對應到的數字
    console.log("沒分數");
    break;
}
//Output:沒分數
```

# 迴圈(loop)控制：for, while

- for

```js
for (let i = 3; i < 10; i += 2) {
  console.log("i:", i);
}
//i++ => i+1
//i+=2 => i+2
//Output:i:3 i:5 i:7 i:9
```

without loop：每個值都要 console.log

```js
//3個人的班級
let classA = [100, 70, 45];
//取出陣列的值
console.log(classA[0]); //classA的第1個
//Output:100
console.log(classA[1]); //classA的第2個
//Output:70
console.log(classA[2]); //classA的第3個
//Output:45
console.log(classA[3]);
//沒有第4個值
//Output:undefined
```

with loop:把 i 設定好，只要 console.log 一次

```js
for (let i = 0; i < 3; i++) {
  console.log("i:", classA[i]);
}
//Output:i:100 i:70 i:45
```

- 用 loop 控制陣列

```js
let classB = [100, 80, 55];
classB.push(60);
console.log("classB:", classB);
//Output:classB: (4) [100, 80, 55, 60]
for (let i = 0; i < classB.length; i++) {
  if (i === 2) {
    classB[i] = 999;
  }
}
console.log("classB:", classB);
//陣列長度不固定時，可以寫classB.length，而不侷限於數字
//i++, 執行完一次i就+1
//當跑到i等於2時，就把值改成999
//Output:classB: (4) [100, 80, 999, 60]
```

- 用 loop 控制物件

without loop

```js
//[物件一、物件二......]
//也可以用let
const Posts = [
  {
    img: "https://fakeimg.pl/600x400",
    date: "2023 / 05 / 24",
  },
  {
    img: "https://fakeimg.pl/300x300",
    date: "2023 / 05 / 25",
  },
];
//當我想選取特定物件時：
const Img1 = {
  img: "https://fakeimg.pl/600x400",
  date: "2023 / 05 / 24",
};
console.log(Img1.img);
//Output:https://fakeimg.pl/600x400
console.log(Img1.date);
//Output:2023 / 05 / 24
```

with loop

```js
const Posts = [
  {
    img: "https://fakeimg.pl/600x400",
    date: "2023 / 05 / 24",
  },
  {
    img: "https://fakeimg.pl/300x300",
    date: "2023 / 05 / 25",
  },
];
//當我想選取特定物件時：
for (let i = 0; i < Posts.length; i++) {
  if (i === 0) {
    let Img1 = Posts[i];
    console.log(Img1);
  }
}
//Output:{img: 'https://fakeimg.pl/600x400', date: '2023 / 05 / 24'}
```

- while：用 boolean 作為條件判斷

```js
let condition = true;
//不要馬上console.log，會跑到當機
let target = 10;
let i = 0;

while (condition) {
  if (i === target) {
    condition = false;
  }
  console.log(i);
  i++;
}
//Output:0 1 2 3 4 5 6 7 8 9 10
```

# 函數：function

- 宣告

```js
function hello() {
  console.log("你好");
}
//僅宣告，沒有Output
```

- 執行

```js
function hello() {
  console.log("你好");
}
hello();
//Output:你好
```

- 應用:讓 code 有共通邏輯，需調整時能夠統一調整。

example:

```js
//購物金額：商品＋商品-折價券
function addMoney() {
  console.log(100 + 200 - 50);
}

//購物車頁面
addMoney();
//Output:250

//結帳頁面
addMoney();
//Output:250
```

- 有參數的 function

```js
function addMoney(price1, price2, discount) {
  console.log(price1 + price2 - discount);
}

//購物車頁面
addMoney(100, 200, 50);
//Output:250

//結帳頁面
addMoney(100, 200, 50);
//Output:250
```

- 有回傳值的 function: return

```js
function addMoney(price1, price2, discount) {
  let result = price1 + price2 - discount;
  return result;
}

let total = addMoney(100, 200, 50);
console.log("total:", total);
//Output:total: 250
```

practice:加入 if else

```js
function addMoney(price1, price2, discount) {
  let result = price1 + price2 - discount;
  let message = "一般會員";

  if (result >= 20000) {
    message = "白金會員";
    return message;
  }
  if (result >= 50000) {
    message = "尊爵會員";
    return message;
  }
  return message;
}
let message0 = addMoney(10000, 20000, 500);
console.log("message:", message0);
//Output:message: 白金會員
```

- 構造函數

```js
function createCard(initName) {
  this.name = initName;
}
//可以一次建立許多物件，並將其標準化

//new =>建立、構造
const a1 = new createCard("Gini1");
const a2 = new createCard("Gini2");
const a3 = new createCard("Gini3");
console.log(a1);
//Output:createCard {name: 'Gini1'}
console.log(a2);
//Output:createCard {name: 'Gini2'}
console.log(a3);
//Output:createCard {name: 'Gini3'}
//每個物件都有name屬性
```

- function 進階宣告方式

```js
let hello = function () {};
```

```js
let hello = () => {};
```

# class 與 this

- class 的基本操作

```js
//類似構造函數
//constructor => 構造函數
class Card {
  constructor(initName) {
    this.name = initName;
  }
}

const c1 = new Card("Gini");
console.log("c1:", c1);
//Output:c1: Card {name: 'Gini'}
console.log(c1.name);
//Output:Gini
```

- this 的基本操作
  跟著當下的執行者做變化

```js
class Card {
  constructor(initName) {
    this.name = initName;
  }
  hello() {
    console.log("hello", this.name);
  }
}

const c1 = new Card("Gini");
c1.hello();
//Output:hello Gini

const a1 = { name: "a1a1a1" };
a1.hellohello = c1.hello;
a1.hellohello();
//Output:hello a1a1a1
```

- class 繼承

```js
//寫兩個 class, 呈父子關係（主從關係）
class Car {
  constructor(initName) {
    this.name = initName;
  }
  start() {
    console.log("車子啟動");
  }
  //Output:車子啟動
}

//extends => 繼承
//繼承 class Car 的 start function
//super =>可調用 class Car 的 constructor
class Porshe extends Car {
  constructor(namePorshe) {
    super(namePorshe);
  }
}

const p1 = new Porshe("保時捷");
p1.start();
console.log("name:", p1.name);
//Output:name: 保時捷
```

super 的另一種應用

```js
class Car {
  constructor(initName) {
    this.name = initName;
  }
  start() {
    console.log("車子啟動");
  }
}

class Porshe extends Car {
  constructor(namePorshe) {
    super(namePorshe);
  }

  //super的另一種應用
  //直接應用class Car 的 function
  start2() {
    super.start();
    console.log("車子排氣");
  }
  //Output:車子排氣
}

const p1 = new Porshe("保時捷");
p1.start2();
console.log("name:", p1.name);
```

承上

```js
class Car {
  constructor(initName) {
    this.name = initName;
  }
  start() {
    console.log("車子啟動");
  }
}

class Porshe extends Car {
  constructor(namePorshe) {
    super(namePorshe);
  }

  //或是直接覆蓋class Car 的 function
  start() {
    console.log("保時捷啟動");
  }
  //Output:保時捷啟動
}

const p1 = new Porshe("保時捷");
p1.start();
console.log("name:", p1.name);
```

```js
//若覆蓋後再用super.start()，
//可使父層和子層的function都能用

  start() {
    super.start();
    console.log("保時捷啟動");
  }
```
