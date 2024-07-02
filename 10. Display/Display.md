# Display

- When we apply css to a block element, It'll stack on eachother.

```css
main {
  background-color: aqua;
  width: 50%;
}

p {
  background-color: lightgray;
}
```

- Here, `main` & `p` both are block level element & we can see that background color of element `p` is over the element `main`.
- We can see that `p` element's background color is taking 100% of `main` element's space.

- We cannot apply top or bottom margin , height to an **inline element** (untill & unless we make it display block).
- Inline element don't stack on eachother & don't create a new line.