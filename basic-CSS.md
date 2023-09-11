# CSS length units

### Absolute:絕對

- px
- in

```css
/* px */

.wrap {
  width: 400px;
}
```

```css
/* in */

.wrap {
  width: 4in;
}
```

### Relative:相對

- rem
- Points
- Pica
- viewport width
- viewport height

```css
/* rem */

.wrap {
  width: 40rem;
}
```

```css
/* Points */

.wrap {
  width: 120pt;
}
```

```css
/* Pica */

.wrap {
  width: 12pc;
}
```

```css
/* viewport width */

.wrap {
  width: 10vw;
}
```

```css
/* viewport height */

.wrap {
  width: 10vh;
}
```

1em == 16px == 0.17in == 12pt == 1pc == 4.2mm == 0.42cm

- Percentage
  - Percentage isn’t technically a length unit, but I’m including it here since it is so related.
  - For example, if an element renders at 450px width, a child element with a width set to 50% will render at 225px.

```css
/* Percentage */

.wrap {
  width: 50%;
}
```

# CSS Colors

### RGB

- red: 0-255, green: 0-255, blue: 0-255

```css
body {
  background-color: rgb(255, 0, 255);
}
```

### Hexadecimal

- red: 00-FF, green: 00-FF, blue: 00-FF

```css
body {
  background-color: #ff00ff;
}
```

# RWD (Responsive Web Design): 回應式設計

- Media Query: 根據螢幕寬度，調整 CSS 設定

```css
@media (max-width: 1200px){
  螢幕寬度在 1200px 以下
};
```

- flex-wrap: 將左右並排調整成上下並排

```css
@media (max-width: 1200px) {
  .list {
    flex-wrap: wrap;
  }
}
```

- br 的顯示和隱藏，控制內容是否換行

```css
/* 換行 */
br {
  display: block;
}

/* 不換行 */
br {
  display: none;
}
```

- 利用顯示和隱藏決定要展示的版面

```html
<div class="desktop">
  電腦版
  <div>
    <div class="mobile">
      手機版
      <div></div>
    </div>
  </div>
</div>
```

```css
.desktop {
  display: block;
}
.mobile {
  display: none;
}

@media (max-width: 500px) {
  /* 螢幕寬度在 500px 以下 */
  .desktop {
    display: none;
  }
  .mobile {
    display: block;
  }
}
```
