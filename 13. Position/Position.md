# Position

- `position` property specifies the type of positioning method used for an element.

- There are five different position values:
    1. `static` (Default Value)
    2. `relative`
    3. `fixed`
    4. `absolute`
    5. `sticky`

- Elements are then positioned using the top, bottom, left, and right properties, these properties will not work unless the `position` property is set first, They also work differently depending on the position value.

## `position: static;`

- Static positioned elements are not affected by the top, bottom, left, and right properties.
- An element with `position: static` is not positioned in any special way; it is always positioned according to the normal flow of the page.

## `position: relative;`

- An element with `position: relative` is positioned relative to its normal position.
- Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position, Other content will not be adjusted to fit into any gap left by the element.
- The element is relative to its normal position.

## `position: fixed;`

- An element with `position: fixed` is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element.
- A fixed element does not leave a gap in the page where it would normally have been located.
- The element is relative to the viewport.

## `position: absolute;`

- An element with `position: absolute` is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed).
- If an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling.
- Absolute positioned elements are removed from the normal flow, and can overlap elements.
- The element is relative to the nearest positioned ancestor (not static).

## `position: sticky;`

- An element with `position: sticky` is positioned based on the user's scroll position.
- A sticky element toggles between `relative` and `fixed`, depending on the scroll position. It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place (like position:fixed).
- The element is treated as `relative` until it crosses a specified threshold, after which it is treated as `fixed`.

## Example : 01

```html
    <div class="outer-container">
        <div class="inner-container">
            <div class="box absolute">
                <p>Absolute</p>
            </div>
            <div class="box relative">
                <p>Relative</p>
            </div>
            <div class="box fixed">
                <p>Fixed</p>
            </div>
            <div class="box sticky">
                <p>Sticky</p>
            </div>
        </div>
    </div>
```

- Here, We define the classes `outer-container`, `inner-container`, `box`, `absolute` (for absolute position), `relative` (for relative position), `fixed` (for fixed position), `sticky` (for sticky position).
- CSS properties are as below,

```css
.outer-container {
  border: 3px dashed #000;
  width: 75vw;
  height: 85vh;
  margin: 40px auto;
  position: relative;
}

.inner-container {
  border: 2px solid #00f;
  width: 40vw;
  height: 50vh;
  margin: 200px auto;
}

.box {
  width: 150px;
  height: 150px;
  color: #fff;
  padding: 1rem;
}

.absolute {
  background-color: #00f;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
}

.relative {
  background-color: #f00;
  position: relative;
  top: 300px;
  left: 100px;
}

.fixed {
  background-color: green;
  position: fixed;
  top: 100px;
}

.sticky {
  background-color: #000;
  position: sticky;
  top: 0;
}
```

- Here, `outer-container` class is `relative` & `inner-container` class is `static` (default value).
- `absolute` class is `absolute` positioned so it'll relative to its nearest positioned ancestor (which is not static) which is `outer-container` class.
- `relative` class is `relative` positioned so it'll relative to its normal position which is inside the `inner-container` class so it'll relative to `inner-container` class.
- `fixed` class is `fixed` positioned so it'll relative to viewport which means it stays in the same place.
- `sticky` class is `sticky` positioned so it'll treated as `relative` untill it crossed `top: 0`, after which it's treated as `fixed`.

- `z-index` controls the stacking order of overlapping elements on a page.

## Example : 02

```html
    <button class="social">🚀</button>
    <section id="one">
        <header class="blue">Header One</header>
        <h2>One</h2>
    </section>
    <section id="two">
        <header class="red">Header Two</header>
        <h2>Two</h2>
    </section>
    <section id="three">
        <header class="green">Header Three</header>
        <h2>Three</h2>
    </section>
    <footer>
        <a href="#one">One</a> | 
        <a href="#two">Two</a> | 
        <a href="#three">Three</a>
    </footer>
```

- It's a basic HTML webpage which has CSS property as below,

```css
html { scroll-behavior: smooth; }

section {
  height: 100vh;
}

.blue { background-color: #00f;}
.red { background-color: #f00;}
.green { background-color: green;}

header, footer {
  color: #fff;
  text-align: center;
  height: 100px;
}

header {
  position: sticky;
  top: 0;
  font-size: 5rem;
}

footer {
  background-color: #000;
  position: sticky;
  bottom: 0;
  font-size: 3rem;
}

a:visited {
  color: #fff;
}

.social {
  background-color: royalblue;
  color: #fff;
  font-size: inherit;
  padding: 1rem;
  position: fixed;
  top: 30%;
  left: 0;
  z-index: 1;
}
```

- `scroll-behavior` specifies whether to smoothly animate the scroll position, instead of a straight jump, when the user clicks on a link within a scrollable box.


- The best way to disappear something from webpage without commenting it or removing from code is to set its position `left: -10000px`.