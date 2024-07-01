# Box Model

- In CSS, Everything is a Box.
- For Opening DevTools for any HTML page : `CTRL + SHIFT + I`
- In Element Tab of DevTool, which ever element you select it will highlight on the webpage with different colours.

- After selecting `h1` element in `header` element, It'll highlight on the webpage in form of box with different colours.
- It's known as Box Model.

- Orange colour represents **Margin**.
- Border is represented as dashed red color.
- Inside the border, Green color represents **Padding** & Blue color represents **Content**.

- There is a tab named as **Computed** beside **Styles**, contains a box model & shows the size of each one (content, padding, border, margin) in pixel.

```css
h1 {
    border: 2px dashed red;
    width: 50%;
    font-size: 3rem;
    padding: 0.5em;
}
```

- From the box model & above CSS code, We can compare the size.
    border : 2px & 1.600 (in box model)
    margin : 32.160 (in box model)

- In **Styles** tab, We can see the *user agent stylesheet* of `h1` element, where `margin-block-start: 0.67em` (2/3 em) which is in unit `em` which is respond to `font-size: 3rem` (48px), so 2/3 of 48px is nearly 32px which is match with margin size in box model 32.160px (Our `font-size` impacting on size of default margin).

- If we want to take control of the `margin` & `padding` (which doesn't effect due to any other element), We use our **wild card** as below,

```css
* {
    margin: 0;
    padding: 0;
}
```

- After applying this, we can see in the box model, All the default margin & padding is taken away & its set to 24px of padding as it is 0.5em, which is in unit `em` which is respond to `font-size: 3rem` (48px), so 0.5 of 48px is 24px which is match with padding size in box model.

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: content-box;
}
```

- Default value of `box-sizing` is `content-box`, so we cannot see any change but if we change the `width` of `h1` element, then we can see the change in size (inside box model).

```css
h1 {
    border: 2px dashed red;
    width: 400px;
    font-size: 3rem;
    padding: 0.5em;
}
```

- As we set the `width` to **400px**, now it's fixed to 400px (We can show in Box Model), It doesn't include the size of `padding` or `border` or `margin`.

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

- If we change the value of `box-sizing` to `border-box` & `width` is **400px**, then we can see the change in Box Model, the size of content in box model is changed to nearly 348.800px & padding is set to 24px & border is set to nearly 1.600px, all together is nearly 400px.

- If we want to make the similar change in `header` element & `main` element, we define a class named `container` in both element as below,

```html
<header class="container">
    ...
</header>
<main class="container">
    ...
</main>
```

```css
.container {
    border: 10px double red;
    font-size: 1.5rem;
    margin: 1.5em;
    padding: 1.5em;
    outline: 5px solid purple;
    outline-offset: -20px;
}
```

- We can change the margin & padding of each side separately by using `margin-top`, `margin-right`, `margin-bottom`, `margin-left`, `padding-top`, `padding-right`, `padding-bottom`, `padding-left`.
- If we want to change any particular property of any particular side, we can do it as `border-right-color`, etc.
- `outline-offset` is used to set the distance between border & outline.

```html
<div class="circle"></div>
```

```css
.circle {
    margin: 3rem auto;
    background-color: gold;
    width: 100px;
    height: 100px;
    border: 2px solid #000;
    border-radius: 50px;
    outline: 2px solid red;
    outline-offset: 0.25rem;
}
```

- Here we create a class named **Circle** in div.
- `margin: 3rem auto`, Here `auto` represent that left & right margin will auto adjust & set the circle class in the centre horizontally.
- `border-radius` is used to set the corners rounded, if we set the radius half of its height & width (both are same), it'll become circle.