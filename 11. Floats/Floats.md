# Floats

- We create a block using `div` which has class named as `block`, `left` & `right` which has CSS property as below,

```css
.block {
  width: 30vw;
  height: 30vw;
  background-color: #000;
  color: #fff;
  padding: 1rem;
}

.left {
  float: left;
  margin-right: 1rem;
}

.right {
  float: right;
  margin-left: 1rem;
}
```

- From `block` class, We define the properties of block (like dimensions, color, etc.). From `left` & `right` class, We define the **float** due to which we can set where the block will float beside with texts.

- Here, We create a `section` which has CSS properties as below,

```css
section {
  background-color: bisque;
  border: 1px solid #333;
  padding: 1rem;
  display: flow-root;
}
```

- Here, We use `display: flow-root` to set both the elements (Block & Paragraph which is inside the section) into the `section` block, If we don't use it, the `section` block only cover the paragraph into it & block of `div` will overflow from the `section` block.