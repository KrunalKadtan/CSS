- `min()` function takes two or more values and returns the smallest (minimum) value. This can be useful for setting a value that adapts to different conditions, ensuring that it does not exceed a certain limit

```css
.element {
  width: min(50%, 300px);
}
```

In this example, the width of the element will be the smaller value between 50% of its container’s width or 300px.

- `calc()` function allows you to perform calculations to determine CSS property values. This function can use basic math operations like addition (`+`), subtraction (`-`), multiplication (`*`), and division (`/`).

```css
.element {
  width: calc(100% - 50px);
}
```

In this example, the width of the element will be 100% of its container’s width minus 50 pixels.