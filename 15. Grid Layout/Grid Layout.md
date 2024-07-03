# Grid Layout

- It allows you to create grid-based designs directly in CSS, without the need for extra markup or frameworks.

## 1. Define A Grid Container

- To create a grid layout, you first need to define a grid container. This is the element that will hold the grid items.

```css
.container {
  display: grid; /* or display: inline-grid; */
}
```

## 2. Define Grid Columns & Rows

- You can define the number of columns and rows using the `grid-template-columns` and `grid-template-rows` properties.

```css
.container {
  display: grid;
  grid-template-columns: 100px 200px 100px; /* Three columns with specified widths */
  grid-template-rows: 100px 200px; /* Two rows with specified heights */
}
```

- You can also use fractions (`fr`), percentages, or other units.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr; /* Three columns, where the middle one is twice as wide as the others */
  grid-template-rows: 50% 50%; /* Two rows, each taking up half the container's height */
}
```

## 3. Place Grid Items

- Grid items are the child elements of the grid container. By default, they are placed in the grid cells in the order they appear in the HTML.

```html
<div class="container">
  <div class="item1">Item 1</div>
  <div class="item2">Item 2</div>
  <div class="item3">Item 3</div>
</div>
```

- You can explicitly place items in specific grid cells using the `grid-column` and `grid-row` properties.

```css
.item1 {
  grid-column: 1 / 2; /* Start at column 1, end at column 2 */
  grid-row: 1 / 2; /* Start at row 1, end at row 2 */
}

.item2 {
  grid-column: 2 / 4; /* Span columns 2 and 3 */
  grid-row: 1 / 3; /* Span rows 1 and 2 */
}

.item3 {
  grid-column: 1 / 3; /* Span columns 1 and 2 */
  grid-row: 2 / 3; /* Start at row 2, end at row 3 */
}
```

## 4. Grid Gap

- You can add gaps between rows and columns using the `grid-gap`, `grid-row-gap`, and `grid-column-gap` properties.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 100px 100px;
  grid-gap: 10px; /* Gap between both rows and columns */
  /* or */
  grid-row-gap: 10px; /* Gap between rows */
  grid-column-gap: 20px; /* Gap between columns */
}
```

## Example

```html
    <header class="header el"><h1>Header</h1></header>
    <main class="container">
        <div class="box">1</div>
        <div class="box">2</div>
        <div class="box">3</div>
        <div class="box">4</div>
        <div class="box">5</div>
        <div class="box">6</div>
    </main>
    <aside class="sidebar el"><h2>Sidebar</h2></aside>
    <footer class="footer el"><h2>Footer</h2></footer>
```

- Here, We create `header` class, `el` class, `container` class, `box` class, `sidebar` & `footer` class.

```css
body {
  font-family: "Roboto", sans-serif;
  min-height: 100vh;

  display: grid;
  grid-template-columns: repeat(9, 1fr);
  grid-auto-rows: 50px auto 50px;
  grid-template-areas: 
    "hd hd hd hd hd hd hd hd hd" 
    "mn mn mn mn mn mn mn sb sb"
    "ft ft ft ft ft ft ft ft ft";
  column-gap: 0.5rem;
}

.el {
  background-color: rebeccapurple;
  color: #fff;
  display: grid;
  place-content: center;
}

.header {
  grid-area: hd;
}

.sidebar {
  grid-area: sb;
  background-color: #00f;
}

.footer {
  grid-area: ft;
}

.container {
  grid-area: mn;
  min-height: 400px;
  display: grid;
  grid-template-columns: repeat(2, 1fr 2fr);
  grid-auto-rows: minmax(150px, auto);
  gap: 1rem;
}

.box {
  background-color: #000;
  color: #fff;
  font-size: 2rem;
  padding: 0.5rem;
}

.box:first-child {
  background-color: #00f;
  grid-column: 1 / 4;
  grid-row: 1 / 3;

  display: grid;
  place-content: center;
}

.box:nth-child(2) {
  background-color: purple;
  grid-column: 1 / 5;
  grid-row: 3 / 4;
}
```

### `grid-template-columns`

- Defines the width of each column in the grid.

#### Syntax
```css
grid-template-columns: <track-size> ...;
```

- `<track-size>` can be a length (px, %, em, etc.), a fraction (`fr`), the keyword `auto`, or repeat function.

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* Three columns each taking 1 fraction of the available space */
}
```

### `grid-template-rows`

- Defines the height of each row in the grid.

#### Syntax
```css
grid-template-rows: <track-size> ...;
```

- `<track-size>` can be a length (px, %, em, etc.), a fraction (`fr`), the keyword `auto`, or repeat function.

```css
.container {
  display: grid;
  grid-template-rows: repeat(2, 150px); /* Two rows each with a height of 150px */
}
```

### `grid-auto-rows`

- Sets the size of implicitly created rows.

#### Syntax
```css
grid-auto-rows: <track-size>;
```

- `<track-size>` can be a length (px, %, em, etc.), a fraction (`fr`), or the keyword `auto`.

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px; /* Two columns */
  grid-auto-rows: 50px; /* Any additional rows will be 50px high */
}
```

### `grid-auto-columns`

- Sets the size of implicitly created columns.

#### Syntax
```css
grid-auto-columns: <track-size>;
```

- `<track-size>` can be a length (px, %, em, etc.), a fraction (`fr`), or the keyword `auto`.

```css
.container {
  display: grid;
  grid-template-rows: 100px 100px; /* Two rows */
  grid-auto-columns: 50px; /* Any additional columns will be 50px wide */
}
```

### `grid-template-areas`

- Allows you to assign names to specific sections of the grid and then place grid items into those named areas.

#### Defining Grid Template Areas

1. Define Named Areas in the Grid Container
2. Assign Grid Items to Named Areas

#### Step 1 : Define Named Areas

- You define the named areas in the grid container using the `grid-template-areas` property. Each named area is specified as a string in a grid of strings, representing the layout.

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
  grid-template-rows: 100px 100px;
  grid-template-areas: 
    "header header header"
    "sidebar main main"
    "sidebar footer footer";
}
```

- In this example:

    - The first row has three columns, all named `header`.
    - The second row has one `sidebar` column and two `main` columns.
    - The third row has one `sidebar` column and two `footer` columns.

#### Step 2 : Assign Grid Items to Named Areas

- You can place grid items into these named areas using the `grid-area` property.

```css
    .header {
      grid-area: header;
      background: lightblue;
    }
    .sidebar {
      grid-area: sidebar;
      background: lightcoral;
    }
    .main {
      grid-area: main;
      background: lightgreen;
    }
    .footer {
      grid-area: footer;
      background: lightgoldenrodyellow;
    }
```

- In this example:

    - The grid container uses `grid-template-areas` to define a layout.
    - Each grid item (`header`, `sidebar`, `main`, and `footer`) is placed into a specific area using the `grid-area` property.

#### Advanced Usage

- You can also use the period (`.`) character to represent empty grid cells, and the `grid-area` property in shorthand form to span multiple cells.

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
  grid-template-rows: 100px 100px;
  grid-template-areas: 
    "header header header"
    "sidebar . main"
    "sidebar footer footer";
  gap: 10px;
}
```

- In this example:

    - The middle cell in the second row is empty (`.`).
    - The `main` area spans two columns.

### `place-content`

- The `place-content` property is a shorthand for setting both `align-content` and `justify-content` at the same time. This property is used to align the grid container's content (the grid tracks) within the grid container itself.

#### Syntax
```css
place-content: <align-content> <justify-content>;
```

- `align-content` : Aligns the content along the block (vertical) axis.
- `justify-content` : Aligns the content along the inline (horizontal) axis.

#### Values

- `start` : Aligns the content to the start of the container.
- `end` : Aligns the content to the end of the container.
- `center` : Centers the content within the container.
- `stretch` : Stretches the content to fill the container.
- `space-between` : Distributes the content with space between items.
- `space-around` : Distributes the content with space around items.
- `space-evenly` : Distributes the content with equal space between and around items.

#

Practice Grid Layout Here : https://cssgridgarden.com/