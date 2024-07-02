# Colors

 * We can declare background colour by `background-color:` or only just `background:`.

 * We can choose font colour by `color:`.

 * There is different types of method for defining colour.
    1. Direct Colour Name
    2. RGB/RGBA Value
    3. Hexadecimal Colour Code
    4. Colour Palette
    5. HSL/HSLA Value

# RGB / RGBA Value

 * RGB stands for Red, Blue, Green. It has range of **0** to **255** for each of 3 colours.
 * We can set red colour by `rgb(255, 0, 0)`. For green `rgb(0, 255, 0)`, & for blue `rgb(0, 0, 255)`. For Black `rgb(0, 0, 0)` & White `rgb(255, 255, 255)`.
 * A stands for Alpha which is basically works as opacity. Its range is from **0** to **1**.

 ```css
 body {
    font-size: 22px;
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.5;
    background: papayawhip;
    color: rgb(0,0,0);
 }

 p {
    color: rgba(0,0,0,0.5);
 }
 ```
 * Here, we overide the paragraph color from `rgb(0,0,0)` to `rgba(0,0,0,0.5)`.

# Hexadecimal Colour Code

 * It's also works like RGB. It has range of number **0** to **9** & alphabet **a**/**A** to **f**/**F**.
 * We can set black colour by `#000000` (short hand `#000`). Here **#** is representation of hexadecimal colour code & first 2-digits represented as r-Red, another 2-digits represented as g-Green, & last 2-digits represented as b-Blue. For White `#ffffff` or `#FFFFFF` (short hand `#fff`).
 * For Red `#FF0000` (short hand `#f00`), for Green `#00FF00` (short hand `#0f0`), for Blue `#0000FF` (short hand `#00f`).

# Colour Palette

 * We can open colour paletee by moving our cursor to the colour box beside our colour-name or rgb-value or hex-code.
 * We can choose different colurs by moving a circle & bar on the colour.

# HSL / HSLA Value

 * HSL stands for Hue, Saturation & Lightness & A stands for Alpha (Opacity).
 * For Red `hsl(0, 100%, 50%)`, For white `hsl(0, 0%, 100%)`, For black `hsl(0, 0%, 0%)`
 * Range of Hue is **0** to **359**, It represent different colours from colour wheel.

#

 * Colour Palette Picking & Contrast Checker Tool : https://coolors.co/