# Functions

- CSS functions allow you to perform various operations or transformations directly within your stylesheets.

#### `calc()`
The `calc()` function is used for performing calculations to determine CSS property values. It supports basic arithmetic operations like addition (`+`), subtraction (`-`), multiplication (`*`), and division (`/`).

```css
.element {
  width: calc(100% - 50px);
  padding: calc(10px + 2%);
}
```

#### `var()`
The `var()` function is used to access the value of a custom property (CSS variable).

```css
:root {
  --main-color: #3498db;
}

.element {
  background-color: var(--main-color);
}
```

#### `rgb()`, `rgba()`, `hsl()`, `hsla()`
These functions are used to define colors. The `rgba()` and `hsla()` variants include an alpha (transparency) component.

```css
.element {
  background-color: rgb(255, 0, 0); /* Red */
  color: rgba(255, 255, 255, 0.8); /* White with 80% opacity */
  border: 1px solid hsl(120, 100%, 50%); /* Pure green */
  box-shadow: 0 0 10px hsla(0, 0%, 0%, 0.5); /* Black shadow with 50% opacity */
}
```

#### `url()`
The `url()` function is used to include external resources, such as images, fonts, or other media.

```css
.element {
  background-image: url('background.jpg');
}
```

#### `min()`, `max()`, and `clamp()`
These functions are used to set constraints on CSS property values.

- **`min()`**: Takes multiple values and uses the smallest one.
- **`max()`**: Takes multiple values and uses the largest one.
- **`minmax()`**: Takes 2 values & set 1st one as minimum & 2nd one as maximum.
- **`clamp()`**: Takes three values: a minimum value, a preferred value, and a maximum value. It ensures the value stays within the given range.

```css
.element {
  width: min(50%, 300px);
  height: max(100px, 20vh);
  grid-template-columns: minmax(minimum, maximum);
  font-size: clamp(16px, 2vw, 24px);
}
```

#### `attr()`
The `attr()` function is used to retrieve the value of an attribute of the selected element and use it in the stylesheet. It’s most commonly used with the `content` property in conjunction with `::before` and `::after` pseudo-elements.

```css
a::after {
  content: " (" attr(href) ")";
}
```

#### `rotate()`, `scale()`, `translate()`, `skew()`
These functions are used with the `transform` property to apply various transformations to elements.

```css
.element {
  transform: rotate(45deg) scale(1.5) translateX(100px);
}
```

#### `conic-gradient()`, `linear-gradient()`, `radial-gradient()`
These functions are used to create gradient backgrounds.

```css
.element {
  background: linear-gradient(to right, red, yellow);
  background: radial-gradient(circle, red, yellow, green);
  background: conic-gradient(from 90deg, red, yellow, green);
}
```