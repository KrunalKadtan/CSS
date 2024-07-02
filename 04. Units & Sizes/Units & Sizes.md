# Units & Sizes

 * The following are all **absolute** length units - they are not relative to anything else, & are generally consideredto always be the same size.

| Unit | Name | Equivalent To |
|---|---|---|
| cm | Centimeters | 1cm = 37.8px = 25.2/64in |
| mm | Millimeters | 1mm = 1/10th of 1cm |
| Q | Quarter-millimeters | 1Q = 1/40th of 1cm |
| in | Inches | 1in = 2.54cm = 96px |
| pc | Picas | 1pc = 1/6th of 1in |
| pt | Points | 1pt = 1/72th of 1in |
| px | Pixels| 1px = 1/96th of 1in |

 * Most of these units are more useful when used for print, rather than screen output.
 * For example, we don't typically use `cm` on screen. The only value that we will commonly use is `px` (Pixels).

 * Percentage `%` represents a fraction of some other value. Percentage values are always relative to another quantity. For example, an element's length is relative to its parent element's length.

 ```css
 h1 {
    border: 2px dashed red;
    width: 50%;
 }
 ```
 * Here parent element of `h1` is `header` which has by default width is 100% & width of `h1` relative to it is 50%.

 ```css
 header {
    width: 50%;
 }

 h1 {
    border: 2px dashed red;
    width: 50%;
 }
 ```
 * Here, We define width of `header` 50% of its parent element, so width of `h1` will be 25% wrt parent element of `header` & 50% wrt `header` element.

 ```css
 p {
    font-size: 2rem;
 }
 ```
 * `rem` is refered as **root element**. Here, it'll change the font-size of paragraph by 2X wrt its root element which is `html` or according to browser's default font-size.
 * Default size is 16px so here, It'll be 32px.

 ```css
 main {
    font-size: 2rem;
 }

 p {
    font-size: 2em;
 }
 ```
 * If we use `rm` instead of `rem`, It'll change the size wrt parent element. Here parent element of `p` is `main` element & also in `main` element we change the size wrt root element so size is changed from 16px to 32px & in `p` element size is changed from 32px to 64px (wrt its parent element).

 ```css
 h1 {
    border: 2px dashed red;
    width: 50%;

    font-size: 3rem;
    padding: 0.5em;
 }
 ```
 * Here, font-size will change wrt root element (3X of root element size) & padding size will be wrt `h1` element's font size (that means padding size will be 1.5rem wrt root element), because of `em` instead of `rem`.
 * Here, for padding size, It will not change wrt to any parent element but it will change wrt its own font-size. That's why we take here 0.5em (1.5rem wrt root element).

 ```css
 p {
    font-size: 2rem;
    width: 40ch;
 }
 ```
 * Here `ch` represent character, It's defining that the width of paragraph will be approximately 40 characters.

 ```css
 * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
 }
 ```
 * It'll remove all the default margin & padding.

 ```css
 main {
    width: 50vw;
    background-color: skyblue;
    font-size: 2rem;
 }
 ```
 * By `width: 50vw`, width of `main` element will be 50% of viewport width. Instead of `vw` we can also use `%` (`width: 50%`).
 * By this, we can see width of `p` element is greater than width of `main` element.