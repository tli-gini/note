#＃ 基本變數

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

null:value of nothing

```js
var a = null;
```

undefined:absence of value

```js
var signedIn;
console.log(signedIn);
//Output:undefined
```

NaN:Not-A-Number

```js
"hello" / 5;
//Output:NaN
```

- all of the falsy values:

1. the Boolean value: false
2. the null type
3. the undefined type
4. the number: 0
5. the empty string: ""
6. the odd value: NaN

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

#＃ 陣列（Array）、物件（Object）

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

#＃ 流程控制：if else, switch case

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

#＃ 迴圈(loop)控制：for, while

- for

```js
for (start; stop; step) {
  // do this thing
}
```

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

#＃ 函數：function

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

#＃ class 與 this

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

### Udacity Quiz

- Quiz: JuliaJames
  - Directions:
    Write a while loop that:

1.  Loop through the numbers 1 to 20
2.  If the number is divisible by 3, print "Julia"
3.  If the number is divisible by 5, print "James"
4.  If the number is divisible by 3 and 5, print "JuliaJames"
5.  If the number is not divisible by 3 or 5, print the number

```js
/*
 * QUIZ REQUIREMENTS
 * - Your code should have a variable `x` with a starting value of `1`
 * - Your code should include a `while` loop
 * - Your `while` loop should have a stop condition
 * - Your code should use a conditional statement
 * - Your code should increment `x` by `1` each time the loop executes
 * - Your code should produce the expected output
 * - Your code should not be empty
 * - BE CAREFUL ABOUT THE PUNCTUATION AND THE EXACT WORDS TO BE PRINTED.
 */
```

My solution 1:

```js
var x = 1;

while (x <= 20) {
  switch (x) {
    case 3:
    case 6:
    case 9:
    case 12:
    case 18:
      console.log("Julia");
      break;

    case 5:
    case 10:
    case 20:
      console.log("James");
      break;

    case 15:
      console.log("JuliaJames");
      break;

    default:
      console.log(x);
      break;
  }
  x++;
}

//Output:1 2 Julia 4 James Julia 7 8 Julia James 11 Julia 13 14 JuliaJames 16 17 Julia 19 James

/*
What Went Wrong:
Your `while` loop is missing a conditional statement. 
Use a conditional statement to check if `x` is divisible by 3, 5, or 3 and 5.
*/
```

My solution 2:

```js
var x = 1;

while (x <= 20) {
  if (x % 3 === 0 && x % 5 !== 0) {
    console.log("Julia");
  } else if (x % 5 === 0 && x % 3 !== 0) {
    console.log("James");
  } else if (x % 3 === 0 && x % 5 === 0) {
    console.log("JuliaJames");
  } else {
    console.log(x);
  }
  x++;
}

//Output:1 2 Julia 4 James Julia 7 8 Julia James 11 Julia 13 14 JuliaJames 16 17 Julia 19 James
```

One of the possible solutions:

```js
var x = 1;

// while loop with a stop condition
while (x <= 20) {
  if (x % 3 === 0 && x % 5 === 0) {
    console.log("JuliaJames");
  } else if (x % 5 === 0) {
    console.log("James");
  } else if (x % 3 === 0) {
    console.log("Julia");
  } else {
    console.log(x);
  }
  // increment x at the end of each loop
  x = x + 1;
}
```

- Quiz: Changing the Loop
  Before: while loop

```js
var x = 9;
while (x >= 1) {
  console.log("hello " + x);
  x--;
}
```

After: for loop

```js
for (let x = 9; x >= 1; x--) {
  console.log("hello " + x);
}
```

- Quiz: Laugh it Off
  Directions:
  Write a function called laugh() that takes one parameter,
  num that represents the number of "ha"s to return.

Here's an example of the output and how to call the function that you will write:

```js
console.log(laugh(3));

//Prints: "hahaha!"

/*
 * QUIZ REQUIREMENTS
 * - Your code should have a `laugh()` function
 * - Your `laugh()` function should have one parameter named `num`
 * - Your `laugh()` function should return the correct number of laughs
 */
```

My solution:

```js
var ha = "";

function laugh(num) {
  for (let a = 0; a < num; a++) {
    ha += "ha";
  }
  ha += "!";
  return ha;
}

console.log(laugh(5));

//Ouput:hahahahaha!
```

One of the possible solutions:

```js
var sound = "";
function laugh(num) {
  for (var x = 0; x < num; x++) {
    sound = sound + "ha";
  }
  sound = sound + "!";
  return sound;
}

console.log(laugh(3));
```

## Event Handling 事件處理

- 事件種類：

  - click 滑鼠點擊
  - mouseover 滑鼠移入
  - mouseout 滑鼠移出
  - mousedown 滑鼠按下
  - mouseup 滑鼠放開

- 事件處理三關鍵

  - 哪個標籤發生事件
  - 事件種類
  - 事件對應的處理函式

- 註冊事件處理函式

  - 基本語法：

  ```html
  <!-- <div 事件名稱="程式碼">標籤內文</div> -->
  <!-- <button 事件名稱="程式碼">標籤內文</button> -->

  <div onclick="change()">Click</div>
  <script>
    function change() {
      document.body.innerHTML = "這是新的字";
    }
  </script>
  ```

- 事件處理範例一：
  - 使用 this 關鍵字代表觸發事件的標籤
  - 點擊改變標籤本身的內文：
  ```html
  <div onclick="change(this)">原本的內文</div>
  <script>
    function change(elem) {
      elem.innerHTML = "新的內文";
    }
    //this 代表這個<div>
  </script>
  ```
- 事件處理範例二：
  - 多個事件搭配使用
  - 滑鼠按住、放開同時運作：
  ```html
  <button onmousedown="down(this)" onmouseup="up(this)">Click</button>
  <script>
    function down(elem) {
      elem.style.color = "red";
    }
    function up(elem) {
      elem.style.color = "blue";
    }
  </script>
  ```

## Object 拷貝/複製

- Object 沒有拷貝或複製的狀況：

```js
let a = { x: 3, y: 4 };
let b = a; //沒有建立新物件，參考到同個物件實體
b.x = 5;
console.log(a.x);

//Ouput:5
```

- Object 的拷貝/複製

```js
let a = { x: 3, y: 4 };
let b = { ...a }; //建立新物件，同時複製原物件的資料
b.x = 5;
console.log(a.x);

//Ouput:3
```

- 淺拷貝：Shallow Copy

1. 僅拷貝物件的第一層資料
   a. 物件中包含其他物件，產生層次
   b. 常見的拷貝語法工具都是淺拷貝

```js
let a = { x: 3, y: 4, data: [1, 2, 3] };
//data 為第二層資料

//使用其餘運算符號...拷貝
let b = { ...a };

//使用內建方法 Object.assign()拷貝
let c = Object.assign({}, a);
```

2. 第二層以上的資料不會真的拷貝，仍參考到原來的物件實體
3. 沒有真正拷貝的資料，會互相影響

```js
let a = { x: 3, y: 4, data: [1, 2, 3] };
//data 中的資料沒有真的被拷貝
//物件a和b中的data仍參考到原來的物件實體
let b = { ...a };
b.data[0] = 4; //b對data的操作影響到a的data

console.log(a.data);
//Ouput:[4, 2, 3]
```

- 深拷貝：Deep Copy

1. 完全拷貝物件底下所有層次的資料
   a. 使用 JSON.stringify() 將物件字串化(serialize)
   b. 使用 JSON.parse() 根據字串化的資料重新建立物件結構，完成深拷貝

```js
let a = { x: 3, y: 4, data: [1, 2, 3] };

//將物件結構字串化
let str = JSON.stringify(a);

//根據字串化的資料重新建立物件結構
let b = JSON.parse(str);
```

2. 拷貝後的物件和原來的物件完全分開獨立

```js
let a = { x: 3, y: 4, data: [1, 2, 3] };
let str = JSON.stringify(a);
let b = JSON.parse(str);
//以上完成深拷貝，兩個物件完全獨立且不互相影響且不互相影響

b.data[0] = 4; //b對data的操作不影響a的data

console.log(a.data);
//Ouput:[1, 2, 3]
```

3. 無法拷貝函數、Symbol 等資料（即不能字串化的資料）

```js
let a = {
  x: 3,
  y: 4,
  test: function () {
    console.log("Hello");
  },
};
let str = JSON.stringify(a);
let b = JSON.parse(str);
//test是函數，無法拷貝

b.test();
//Error!
```
