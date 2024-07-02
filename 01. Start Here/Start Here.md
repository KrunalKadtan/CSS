# CSS (Cascading Style Sheets)

 * It's a stylesheet language used to describe the presentation of a document written in HTML or XML.
 * CSS describes how elements should be rendered on screen, on peper, in speech or on other media.

 * HTML is foundation or structure & CSS is a paint, wallpaper or any decoration of a presentation.

# Apply CSS to Document

 * There 3 different ways to apply CSS to our document :
   1. External Stylesheet
   2. Internal Stylesheet
   3. CSS In-Line within Element

 * **External Stylesheet :**
 ```html
    // link in HTML File
    <link rel="stylesheet" href="style.css">
 ``` 
 ```css
    // CSS File
    p
    {
        font-size: 64px;
        color: purple;
    }
 ```
   * `p` --> Selector
   * `color` --> Property
   * `purple` --> Property Value
   * `color: purple` --> Declaration

 * **Internal Stylesheet :**
 ```html
    // in HTML File
    <style>
        p
        {
            color: limegreen;
        }
    </style>
 ```

 * **CSS in-line :**
 ```html
    <p style="color: blue">I'm learning CSS..!</p>
 ```

 * Whichever stylesheet written first it'll rendered first & than another.

 * We'll use External Stylesheet.

 * We can validate our CSS file on https://jigsaw.w3.org/css-validator/#validate_by_upload.