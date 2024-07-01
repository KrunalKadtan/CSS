# Typography

- Typography is the way that text is arranged & presented.

```css
body {
    padding: 10%;
    font-size: 2rem;
}
```

- Here, we set the padding to 10% & font size to 2rem, It'll change the font size of all the  element but font size of input & button will remain same.
- To set the input & button font size same as body, we will inherit it from body as below,

```css
input, button {
    font: inherit;
}
```

- In CSS, We have some text settings which are not affected by font settings at all.
- `text-decoration` is used which has multiple values like **underline**, **overline**, **line-through**, **none** (which is default value), etc. We can use **none** value to remove the underline from the *link* text (which has underline by default).
- `text-transform` is used which has values like **capitalize**, **lowercase**, **uppercase**, etc.
- `text-align` is used which has values like **center**, **left**, **right**, **end**, etc.
- `text-indent` is used to control the horizontal spacing of the first line of block of text or block-level element.
- `line-height` is used to set the distance between lines of text. Improve readability of paragraph.
- `letter-spacing` is used to adjusts the space between characters in a line or block of text.
- `font-weight` is used to control the thickness of text.
- `font-style` is used to create a unique look & has values like **italic**, **oblique**, etc.
- `font-family` is used which has values like **serif**, **monospace**, **cursive**, etc.