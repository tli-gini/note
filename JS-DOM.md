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
