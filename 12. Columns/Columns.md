# Columns

- We can set the paragraphs columnwise by using `columns` in CSS as below,

```css
.columns {
  /* column-count: 4;
  column-width: 250px; */
  columns: 4 250px;
  column-rule: 3px solid #333;
  column-gap: 3rem;
}
```

- `column-count` is used to show our content in column form (it's represents the number of columns).
- `column-width` define the width of the column.
- If We set the `column-width` & `column-count` both then number of column will be variable according to size of viewport, the maximum number of column will appear according to value of `column-count`.
- `columns` is the short hand for both `column-count` & `column-width`, we define both the values at once in `columns`.
- `column-rule` set the line between 2 columns.
- `column-gap` define the distance between 2 columns.

- Here, We also add a **Quote** between the column as below,

```html
<p class="quote">&#8220;Where's my rug, man?&#8221; <span class="nowrap"></span>&#8212;The Dude</span></p>
```

```css
.columns .quote {
  margin-top: 2rem;
  font-size: 3rem;
  text-align: center;
  color: #333;
  column-span: all;
}

.npwrap {
  white-space: nowrap;
}
```

- `.columns .quote` represent the `quote` class inside the `columns` class.
- `column-span` allows an element to span across multiple columns.
- `white-space` specifies how white-space inside an element is handled.
- `&#8220;` represent **&#8220;** & `&#8221;` represent **&#8221;** & `&#8212;` represent **&#8212;**.