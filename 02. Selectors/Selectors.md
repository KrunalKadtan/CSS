# Selectors

 * There are 3 levels of Selctors which are most common.
   1. Element Selector
   2. Class Selector
   3. ID Selector

# Element Selector

 ```
   body
   {
      font-size: 22px;
      border: 3px solid black;
   }
 ```
 * `font-size` will increase the size of all the fonts in body element.
 * It'll happen due to inheritance, all other elemets will inherit this property from body.
 * Here, dur to `border`, a border created only over body element (Not inherite into all the elements under body) (Black Border).

 ```
   p
   {
      color: purple;
   }
 ```
 * It'll change the colour of all the fonts in that element (`p` / Paragraph Element).

 ```
   h1, h2
   {
      color: blue;
   }
 ```
 * We can also group selectors (here we grouped `h1` & `h2`), we can group the selectors by putting `,` in between them.
 * If we don't put `,` in between them then it'll be looking for any `h2` that exist or nested inside `h1`.
 * It'll change colour of all fonts inside `h1` & `h2` elements.

 ```
   p span
   {
      text-transform: uppercase;
      background-color: gold;
   }
 ```
 * It'll transform the text in uppercase which are under `span` element which is inside `p` element & also change the background colour.
 * We can you class (`highlight`) rather than this.

 ```
    button, input, textarea, select
    {
      font: inherit;
    }
 ```
 * Due to this, font setting will be inherit from `body` for `button`, `input`, `textarea` & `select`.

 ```
    html
    {
      font-size: 22px;
    }
 ```
 * We use this element mostly for inherit its value to other elements.

 ```
    main
    {
      font-family: monospace;
    }
 ```
 * It's a semantic element, it'll change the font family of fonts which are inside `main` element (Every fonts except **CSS Selectors**, because they are out of `main` element).

# Class Selector

 ```
   .gray
   {
      color: gray;
   }
 ```
 * for class, we start its declaration with `.`.
 * It'll change colour of fonts which are under class `gray` (Paragraph of Article 2 & 3).
 * Classes are more specific than selecting all the paragraph (by paragraph element).

 ```
   .highlight
   {
      text-transform: uppercase;
      background-color: gold;
   }
 ```

# ID Selector

 ```
   #second
   {
      font-style: italic;
   }
 ```
 * for id, we start its declaration with `#`.
 * It'll change style of fonts which are under `second` id (Paragraph of Article 2).
 * ID are more specific than classes.
 * ID should be only exist one in HTML document, they should be unique.

# Universal Selector

 * It's selecting everything on the page.
 ```
   *
   {
      border: 1px solid green;
   }
 ```
 * It'll add the border to each element on screen.
 * It's not inherited to all the element but it select each element & give border to it.

#

* You can see specificity of selectors on https://specificity.keegan.st/ (so that you can see why they are working & why they are not working).