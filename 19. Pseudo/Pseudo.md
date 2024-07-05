# Pseudo

## Pseudo-classes

- Pseudo-classes are keywords added to selectors that specify a special state of the selected elements.
- They allow you to apply styles to elements based on their state or position in the document.

### Common Pseudo-classes

1. `:hover` : Applies when the user designates an element (with a pointing device), but does not activate it.
```css
a:hover {
  color: red;
}
```
2. `:active` : Applies when an element is being activated by the user.
```css
a:active {
  color: blue;
}
```
3. `:focus` : Applies when an element has received focus (such as when it's clicked or taped, or a keyboard input is directed to it).
```css
input:focus {
  border: 2px solid green;
}
```
4. `:nth-child` : Matches elements based on their position in a group of siblings.
```css
li:nth-child(2) {
  color: orange;
}
```
5. `:first-child` & `:last-child` : Match an element that is the first or last child of its parent.
```css
p:first-child {
  font-weight: bold;
}

p:last-child {
  font-style: italic;
}
```

- Pseudo-classes are used to define the special states of an element (like `:hover`, `:active`, `:nth-child`).

### Useful Pseudo-classes

1. `:any-link` applies to any element that is a hyperlink (`<a>`, `<area>`, or `<link>` element) whether it is visited or unvisited.
```css
:any-link {
  color: blue;
}
```
This will style all hyperlinks with the color blue, regardless of whether they have been visited.

2. `:is()` is used to reduce the specificity of a selector list. It can take a comma-separated list of selectors, and the styles will apply to any element matching any of those selectors.
```css
:is(h1, h2, h3) {
  color: green;
}
```
This will style all `<h1>`, `<h2>`, and `<h3>` elements with the color green.

3. `:where()` is similar to `:is()`, but it always has a specificity of zero. This means it will not increase the specificity of the selector it is used with, making it useful for utility styles.
```css
:where(.container, .wrapper) {
  padding: 20px;
}
```
This will add padding to any element with the class container or wrapper, but without increasing the specificity.

4. `:target` applies to the unique element (if any) with an id matching the fragment identifier of the URL.
```css
:target {
  border: 2px solid red;
}
```
If you navigate to a URL with a fragment identifier (like `#section1`), the element with the id `section1` will get a red border.

5. `:not` is used to exclude elements that match a given selector from the selection.
```css
:not(.excluded) {
  color: green;
}
```
This will apply the green color to all elements except those with the class `excluded`.

## Pseudo-elements

- Pseudo-elements are keywords added to selectors that allow you to style a specific part of an element.

### Common Pseudo-elements

1. `::before` : Inserts content before the content of an element.
```css
p::before {
  content: "Note: ";
  font-weight: bold;
}
```
2. `::after` : Insert content after the content of an element.
```css
p::after {
  content: " (end)";
  font-style: italic;
}
```
3. `::first-line` : Applies styles to the first line of a block-level element.
```css
p::first-line {
  color: purple;
  text-transform: uppercase;
}
```
4. `::first-letter` : Applies styles to the first letter of a block-level element.
```css
p::first-letter {
  font-size: 2em;
  color: red;
}
```

### Useful Pseudo-elements

1. `::selection` styles the portion of an element that is selected by the user.
```css
::selection {
  background: yellow;
  color: black;
}
```
This changes the appearance of text when highlighted by the user.

2. `::placeholder` styles the placeholder text in an input or textarea element.
```css
input::placeholder {
  color: gray;
  font-style: italic;
}
```
This customizes the look of the placeholder text shown in form fields.

3. `::marker` styles the marker box of a list item, such as bullets or numbers.
```css
li::marker {
  color: red;
  font-size: 1.5em;
}
```
This allows you to customize the appearance of list item markers.

4. `::backdrop` styles the background of elements like `<dialog>` when they are displayed.
```css
dialog::backdrop {
  background: rgba(0, 0, 0, 0.8);
}
```
This is useful for styling modal dialog backgrounds.

5. `::file-selector-button` styles the button of an `<input type="file">` element.
```css
input[type="file"]::file-selector-button {
  background-color: blue;
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
}
```
This customizes the appearance of the file input button.

#

```css
.card img:not([alt]) {
  border: 10px solid red;
}
```

It selects `<img>` elements that do not have an `alt` attribute & applies a red border with a width of 10 pixels to the selected images.