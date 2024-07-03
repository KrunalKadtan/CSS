# Images 

## Default Behavior of `<img>` Tag

- By default, an `img` element is an inline element.
- It flows within the text.
- There might be small gaps below the image due to baseline alignment with text.

## 1. Background Images

- You can set an image as the background of an HTML element.

```css
/* Sets a background image */
div {
  background-image: url('path-to-your-image.jpg');
  background-size: cover; /* or contain, auto, etc. */
  background-position: center; /* or top, bottom, left, right */
  background-repeat: no-repeat; /* or repeat, repeat-x, repeat-y */
}
```

## 2. Image in Content

- You can style img tags directly in CSS.

```css
/* Styles for images */
img {
  width: 100%; /* or any specific width */
  height: auto; /* maintains aspect ratio */
  border-radius: 8px; /* adds rounded corners */
  box-shadow: 0 4px 8px rgba(0,0,0,0.1); /* adds shadow */
}
```

## 3. Using `background` Shorthand Property

- You can use the shorthand `background` property to set multiple background properties in one line.

```css
/* Shorthand background property */
div {
  background: url('path-to-your-image.jpg') no-repeat center center / cover;
}
```

## 4. CSS `content` Property with Pseudo-elements

- You can insert images using pseudo-elements like `::before` and `::after`.

```css
/* Using pseudo-elements to insert images */
div::before {
  content: url('path-to-your-image.jpg');
  display: block;
  width: 50px;
  height: 50px;
}
```

## 5. Image Sprites

- Image sprites are a way to reduce the number of HTTP requests by combining multiple images into a single image file. You then use CSS to display only a portion of the image where needed.

```css
/* Example of using an image sprite */
.icon {
  width: 50px;
  height: 50px;
  background: url('sprite-image.png') no-repeat;
}

.icon.home {
  background-position: 0 0;
}

.icon.profile {
  background-position: -50px 0;
}

.icon.settings {
  background-position: -100px 0;
}
```

## Example

```html
    <div class="container">
        <section class="hero">
            <figure class="profile-pic-figure">
                <img src="profile-800x800.png" alt="Profile Picture" title="My Profile Picture" width="800" height="800">
                <figcaption class="offscreen">Jane Doe</figcaption>
            </figure>
            <h1 class="h1">
                <span class="nowrap">Hello 👋</span> 
                <span class="nowrap">I'm Jane</span>
            </h1>
        </section>
    </div>
    <section>
        <p class="clip">Jane</p>
    </section>
```

```css
body {
  background: repeat-y right center url("bubbles.png"), no-repeat linear-gradient(to left, steelblue, #fff);
  background-size: 20%, auto;
}
```

- The `background` property is a shorthand for setting multiple background properties in one declaration. In this case, it sets two layers of background:

1. **First Layer :** An image that repeats vertically and is positioned at the right center.
2. **Second Layer :** A linear gradient that doesn't repeat.

#### First Layer : Image

- **repeat-y :** This means the image (`bubbles.png`) will repeat vertically (up and down).
- **right center :** This positions the background image at the right side and vertically centered.
- **url("bubbles.png") :** This specifies the path to the image file to be used as the background.

#### Second Layer : Gradient

- **no-repeat :** This means the gradient will not repeat.
- **linear-gradient(to left, steelblue, #fff) :** This creates a linear gradient that transitions from steel blue on the right to white on the left.

- The comma (`,`) separates the two background layers. The first layer is the image with its properties, and the second layer is the gradient with its properties.

- The `background-size` property sets the size of the background images. When there are multiple background layers, `background-size` applies to each layer in the same order.

- **20% :** This sets the width of the first background image (bubbles.png) to 20% of the container's width. The height is adjusted automatically to maintain the aspect ratio.
- **auto :** This sets the size of the second background layer (the gradient). Since gradients are not typically sized, `auto` means the gradient will fill the entire container.

1. Background Image :

- The image `bubbles.png` is positioned at the right center and repeats vertically.
- Its width is set to 20% of the container's width.

2. Gradient:

- The linear gradient transitions from steel blue on the right to white on the left.
- The gradient does not repeat and covers the entire container.

```css
.container {
  background-color: rgb(251, 210, 156);
  background-image: url('map-2176x1451.png');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
```

- `background-image: url('map-2176x1451.png');` sets the background image for the container using the specified image file map-2176x1451.png.

- `background-repeat: no-repeat;` ensures that the background image does not repeat. There will be only one instance of the image. `background-repeat` controls whether the image repeats and in which directions.

    - **`repeat` :** The background image repeats both horizontally and vertically. This is the default value.
    - **`repeat-x` :** The background image repeats only horizontally.
    - **`repeat-y` :** The background image repeats only vertically.
    - **`no-repeat` :** The background image does not repeat.
    - **`space` :** The background image is repeated as many times as possible without being clipped, and the extra space is distributed evenly between the repeats.
    - **`round` :** The background image is repeated and rescaled to fit the container.

- `background-position: center;` centers the background image within the container. The image is positioned in the center both horizontally and vertically. `background-position` sets the starting position of the background image.

    - **Keywords :** `left`, `center`, `right`, `top`, `bottom` (combinations like `center center`, `right bottom`, etc.)
    - **Percentages :** `50% 50%` (first value is horizontal position, second is vertical position)
    - **Lengths :** `10px 20px` (first value is horizontal offset, second is vertical offset)

- `background-size: cover;` makes the background image cover the entire container. The image will scale to maintain its aspect ratio while covering the whole area of the container. Parts of the image may be cropped to fit the container's dimensions. `background-size` controls the size of the background image and how it scales.

    - **`auto` :** Default value. The background image is displayed in its original size.
    - **`cover` :** Scales the image to cover the entire element, maintaining the aspect ratio. Parts of the image may be clipped.
    - **`contain` :** Scales the image to fit within the element while maintaining the aspect ratio. The entire image is visible.
    - **Lengths :** `100px 200px` (first value is width, second is height)
    - **Percentages :** `50% 50%` (first value is width, second is height)

```css
.h1 {
  font-size: 500%;
  color: aliceblue;
  text-shadow: 2px 2px 5px #000;
}
```

- `text-shadow` is used to add shadows to text. This property allows you to create a variety of visual effects, from subtle shadows to dramatic highlights.

#### Syntax
```css
text-shadow: h-offset v-offset blur-radius color;
```

- **h-offset :** The horizontal offset of the shadow. Positive values move the shadow to the right, while negative values move it to the left.
- **v-offset :** The vertical offset of the shadow. Positive values move the shadow down, while negative values move it up.
- **blur-radius (optional) :** The blur radius. The higher the number, the more blurred the shadow will be. If omitted, the default is `0` (a sharp shadow).
- **color (optional) :** The color of the shadow. If omitted, the default color is `black`.

#### Basic Shadow

- A simple shadow with horizontal and vertical offsets :

```css
h1 {
  text-shadow: 2px 2px;
}
```

- This creates a shadow 2 pixels to the right and 2 pixels below the text.

#### Shadow With Blur

- Adding a blur effect to the shadow :

```css
p {
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
}
```

- This creates a shadow 2 pixels to the right and 2 pixels below the text, with a blur radius of 5 pixels and a semi-transparent black color.

#### Multiple Shadows

- You can apply multiple shadows to the same text by separating each shadow with a comma :

```css
h2 {
  text-shadow: 1px 1px 2px black, 0 0 5px blue, 0 0 10px red;
}
```

- This creates three shadows: a black shadow with a slight offset and blur, a blue glow, and a larger red glow.

#### Glowing Text Effect

- Creating a glowing text effect by using multiple shadows :

```css
.glow {
  text-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 15px #ff00ff, 0 0 20px #ff00ff, 0 0 25px #ff00ff, 0 0 30px #ff00ff, 0 0 35px #ff00ff;
}
```

- This creates a glowing effect by stacking multiple shadows with increasing blur radii.

#### 3D Text Effect

- Creating a 3D text effect using shadows with different offsets :

```css
.three-d {
  text-shadow: 1px 1px 0 #ccc, 2px 2px 0 #c9c9c9, 3px 3px 0 #bbb, 4px 4px 0 #b9b9b9, 5px 5px 0 #aaa, 6px 6px 0 #999, 7px 7px 0 #888, 8px 8px 0 #777, 9px 9px 0 #666, 10px 10px 0 #555;
}
```

- This creates a layered 3D effect by applying multiple shadows with increasing offsets.

```css
.clip {
  font-weight: 800;
  font-size: 18rem;
  text-align: center;
  background-image: url("scenic-2200x1331.png");
  background-size: 100%;
  text-transform: uppercase;
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}
```

- `-webkit-background-clip: text;` and `background-clip: text;`, These properties clip the background image to the text. The `-webkit-` prefix is necessary for compatibility with WebKit-based browsers like Chrome and Safari.

- `color: transparent;` makes the text color transparent, allowing the background image to be visible through the text.