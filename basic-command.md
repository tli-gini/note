# Commands

- cd: change directory
- mkdir: make directory
- touch: create a file
- ls: list the files

# JavaScript-functions

- executing a block of code
- fundamental building block

Exercise:

1. Create 3 buttons and 3 variables
2. Each button invokes a separate function
3. Each function adds one every time a button is clicked
4. All the 3 variable values are output to the h2 element

First Try:

```html
<html>
  <head>
    <title>JavaScript</title>
  </head>
  <body>
    <h2 id="firstH2">JavaScript 1</h2>
    <button type="button" onclick="message1('Hello!')">Button 1</button>
    <h2 id="secondH2">JavaScript 2</h2>
    <button type="button" onclick="message2('Nice!')">Button 2</button>
    <h2 id="thirdH2">JavaScript 3</h2>
    <button type="button" onclick="message3('World!')">Button 3</button>
    <script>
      var b = 0;
      function message1(a) {
        b++;
        var Output1 = a + " " + b;
        const firstH2 = document.getElementById("firstH2");
        document.querySelector("#firstH2").innerHTML = Output1;
        console.log(a);
      }
      var d = 0;
      function message2(c) {
        d++;
        var Output2 = c + " " + d;
        const secondH2 = document.getElementById("secondH2");
        document.querySelector("#secondH2").innerHTML = Output2;
        console.log(c);
      }
      var f = 0;
      function message3(e) {
        f++;
        var Output3 = e + " " + f;
        const thirdH2 = document.getElementById("thirdH2");
        document.querySelector("#thirdH2").innerHTML = Output3;
        console.log(e);
      }
    </script>
  </body>
</html>
```

Solution:

```html
<html>
  <head>
    <title>JavaScript</title>
  </head>
  <body>
    <h2>JavaScript</h2>
    <button type="button" onclick="message1()">Click 1</button>
    <button type="button" onclick="message2()">Click 2</button>
    <button type="button" onclick="message3()">Click 3</button>
    <script>
      var var1, var2, var3;
      var1 = var2 = var3 = 0;

      function message1() {
        var1++;
        message();
      }
      function message2() {
        var2++;
        message();
      }
      function message3() {
        var3++;
        message();
      }
      function message() {
        document.querySelector("h2").innerHTML = var1 + " " + var2 + " " + var3;
      }
    </script>
  </body>
</html>
```

# JavaScript-Document Object Model (DOM)

-console.dir(document)

Practice: DOM Selection

```html
<script>
  var el1 = document.getElementById("one");
  el1.style.background = "orange";
  console.log(el1);
  //   el1.style.backgroundColor = "blue";

  var el2 = document.getElementsByClassName("highlight");
  console.log(el2);

  var el3 = document.getElementsByTagName("li");
  console.log(el3);

  var el4 = document.querySelector(".highlight");
  console.log(el4);

  var el5 = document.querySelectorAll(".highlight");
  console.log(el5);
  el5[1].style.color = "yellow";
  el5[1].style.backgroundColor = "blue";
</script>
```

Practice: Element Text Manipulation

```html
<script>
  var el1 = document.querySelector(".highlight");
  console.log(el1);
  console.dir(el1);
  //only first class="highlight"

  el1.innerHTML = "hello! <br> world!";
  console.log(el1.innerHTML);
  //Output:hello! <br> world!

  el1.textContent = "HELLO! <br> WORLD!";
  console.log(el1.textContent);
  //Output:HELLO! <br> WORLD!
  //textContent:純文本。

  el1.outerHTML = "Hello! <br> World!";
  console.log(el1.outerHTML);
  //Output:<li class="highlight">HELLO! &lt;br&gt; WORLD!</li>
</script>
```

Practice: Change Classes DOM

```html
<style>
  .test1 {
    background-color: aquamarine;
    color: rgba(89, 89, 171, 0.643);
  }
  .test2 {
    color: brown;
  }
  .test3 {
    padding: 10px;
    border: 1px solid black;
    margin: 10px;
  }
</style>
<body>
  <h1 class="test3">Lorem ipsum dolor sit amet consectetuer adipiscing elit</h1>

  <script>
    var el1 = document.querySelector("h1");
    console.dir(el1);
    //el1.className = "test1";
    el1.classList.add("test1");
    console.log(el1);
    //Output:<h1 class="test3 test1"> Lorem ipsum dolor sit amet consectetuer adipiscing elit </h1>

    //Console
    //el1.classList.toggle("test1");
    //Output:False
    //Output:True

    //el1.classList.remove("test1");
  </script>
</body>
```

Practice: Change Styles DOM

```html
<style>
  .test {
    margin: 10px;
    padding: 10px;
    border: 5px dotted palevioletred;
    color: hotpink;
    background-color: cornsilk;
    font-family: cursive;
  }
</style>
<body>
  <h1 class="test">Lorem ipsum dolor sit amet consectetuer adipiscing elit</h1>
  <!-- el1[0] -->
  <p class="test">Aenean commodo ligula eget dolor aenean massa</p>
  <!-- el1[1] -->
  <script>
    var el1 = document.getElementsByClassName("test");
    console.dir(el1);
    console.log(el1[0]);
    var temp = el1[0];
    temp.style.backgroundColor = "khaki";
    temp.style.color = "white";
    temp.style.fontFamily = "fantasy";
    temp.style.border = "7px double brown";
    temp.style.display = "block";
  </script>
</body>
```

Practice: Element Attribute Manipulation

```html
<body>
  <h1>Lorem ipsum dolor sit amet consectetuer adipiscing elit</h1>
  <p>Aenean commodo ligula eget dolor aenean massa</p>
  <a href="https://betterplaceholder.com/" target="_blank"
    ><img src="https://fakeimg.pl/150x150/9e6565/803636"
  /></a>
  <img src="https://fakeimg.pl/350x150/6d659e/483680" />

  <script>
    var el1 = document.getElementsByTagName("a");
    console.log(el1);
    console.log(el1[0]);

    var el2 = document.getElementsByTagName("img");
    console.log(el2);
    console.log(el2[1]);

    var temp = el1[0].getAttribute("href");
    console.log(temp);
    el1[0].setAttribute("href", "https://fonts.google.com/");
    //替換成另一個href

    var newImg = el2[1].getAttribute("src");
    console.log(newImg);
    el2[1].setAttribute("src", "https://fakeimg.pl/250x150/6c9e65/2b7034");
    //替換成另一個img
  </script>
</body>
```

Practice: Events Click
-addEventListener

```html
<style>
  .test {
    color: brown;
    background-color: floralwhite;
  }
</style>
<body>
  <ul>
    <li>Hello World</li>
    <li>Lorem ipsum dolor sit amet consectetuer.</li>
    <li>Aenean commodo ligula eget dolor.</li>
    <li>Aenean massa cum sociis natoque penatibus.</li>
  </ul>
  <script>
    var list = document.querySelectorAll("li");
    for (var abc = 0; abc < list.length; abc++) {
      list[abc].addEventListener("click", function () {
        console.log(this);
        var temp = this.classList.toggle("test");
        console.log(temp);
      });
    }
    //   var el1 = document.querySelector("ul");
    //   el1.addEventListener("click", function () {
    //     console.log("click");
    //     el1.style.backgroundColor = "cornflowerblue";
    //     el1.style.color = "bisque";
    //     el1.style.border = "3px dotted aliceblue";
    //   });
  </script>
</body>
```

Practice:

```html

```
