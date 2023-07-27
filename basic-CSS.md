# CSS length units

- Absolute:絕對
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

- Relative:相對
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

- RGB
  - red: 0-255, green: 0-255, blue: 0-255

```css
body {
  background-color: rgb(255, 0, 255);
}
```

- Hexadecimal
  - red: 00-FF, green: 00-FF, blue: 00-FF

```css
body {
  background-color: #ff00ff;
}
```
