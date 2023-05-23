# Commands

- cd: change directory
- mkdir: make directory
- touch: create a file

# JavaScript-functions

- executing a block of code
- fundamental building block

Exercise:

1. Create 3 buttons and 3 variables
2. Each button invokes a separate function
3. Each function adds one every time a button is clicked
4. All the 3 variable values are output to the h2 element

First Try:

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
