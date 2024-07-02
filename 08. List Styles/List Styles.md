# List Styles

- We can change the type of list style by `list-style-type` which has values like **decimal** (default value), **disc** (bullet points just like unordered list), **lower-alpha**, **upper-alpha**, **lower-greek**, **circle**, **none**, etc.

```html
<ol start="3" reversed>
  <li>Step One</li>
  <li value="25">Step Two</li>
  <li>Step Three</li>
</ol>
```

- We can use different type of attributes like **start**, **reversed**, **value**, etc.

- We can change the position of list style according to text alignment with the help of `list-style-position` which has values **inside** (align to text alignment), **outside**, etc.

- If we change the color of text, it will also change the color of list style.

- We can change the list style by any image using `list-style-image` where we give it a path of image using `url(...)`.

- We can mention type, position & image at once by `list-style: square url(...) inside`.

- To change the color of specific content in list, we can do it as below,

```css
ul li:nth-child(2) {
  color: red;
}
```

- It'll change the color of 2nd content in unordered list.

- To change the marker of list style we use `::marker`.

```css
ul ::marker {
  color: red;
  font-family: fantasy;
  font-size: 1em;
  content: "Only 5$ >> ";
}
```

- `color` will change the color of markers of list.
- `font-size` will change the size of markers.
- `content` will chnage the markers into the given content.
- `font-family` will change the font of content.