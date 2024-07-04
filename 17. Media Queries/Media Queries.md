# Media Query

- Media queries are used to apply styles depending on the conditions of the device, such as its screen size, resolution, or orientation. This allows you to create responsive designs that look good on different devices, from mobile phones to desktop computers.

### Basic Syntax

```html
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```
This `meta` element is important to mention in HTML `head` element.

```css
@media media-type (media-feature) {
    /* CSS rules */
}
```

### Common Media Types

- `all` : Suitable for all devices.
- `screen` : Used for computer screens, tablets, smart-phones, etc.
- `print` : Used for printers.
- `speech` : Intended for speech synthesizers.

### Common Media Features

- `width` and `height` : The width and height of the viewport.
- `min-width` and `max-width` : The minimum and maximum width of the viewport.
- `orientation` : The orientation of the device (portrait or landscape).
- `aspect-ratio` : The ratio of the width to the height of the viewport.
- `resolution` : The resolution of the output device.
- `color` : The number of bits per color component of the output device.
- `color-index` : The number of entries in the color lookup table of the output device.
- `monochrome` : The number of bits per pixel in a monochrome frame buffer.
- `scan` : The scanning process of the output device (progressive or interlaced).
- `grid` : Whether the device is a grid device or a bitmap device.
- `prefers-color-scheme` : Indicates if the user has requested the system use a light or dark color theme.
    - Values : `light`, `dark`, `no-preference`
- `prefers-reduced-motion` : Indicates if the user has requested that the system minimize the amount of non-essential motion.
    - Values : `reduce`, `no-preference`
- `hover` : Indicates if the primary input mechanism can hover over elements.
    - Values : `hover`, `none`

## Examples

### 1. Change Background Color on Small Screens

```css
/* Apply styles for screens smaller than 600px */
@media screen and (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

### 2. Adjust Font Size for Tablets

```css
/* Apply styles for screens between 600px and 900px */
@media screen and (min-width: 600px) and (max-width: 900px) {
    body {
        font-size: 18px;
    }
}
```

### 3. Change Layout for Landscape Mode

```css
/* Apply styles for landscape orientation */
@media screen and (orientation: landscape) {
    body {
        background-color: lightgreen;
    }
}
```

## Using Media Queries with Multiple Features

You can combine multiple media features in a single media query.

```css
/* Apply styles for screens wider than 600px and in portrait mode */
@media screen and (min-width: 600px) and (orientation: portrait) {
    body {
        background-color: lightcoral;
    }
}
```

## Media Queries for Responsive Design

To make a website responsive, you typically use multiple media queries to adjust styles at different breakpoints.

```css
/* Mobile styles */
@media screen and (max-width: 599px) {
    body {
        font-size: 14px;
    }
}

/* Tablet styles */
@media screen and (min-width: 600px) and (max-width: 1199px) {
    body {
        font-size: 16px;
    }
}

/* Desktop styles */
@media screen and (min-width: 1200px) {
    body {
        font-size: 18px;
    }
}
```

#

### Common Media Query breakpoints:

| Breakpoint | Description |
| -------- | ---------- |
| < 481px | Mobile devices |
| 481px — 768px | iPads, Tablets |
| 769px — 1024px | Small screens, laptops |
| 1025px — 1200px | Desktops, large screens |
| 1201px and greater | Extra large screens, TV |

### Bootstrap breakpoints:

| Breakpoint | Description |
| -------- | ---------- |
| < 576px | xs |
| >=576px | small |
| >=768px | medium |
| >=992px | large |
| >=1200px | xl |
| >=1400px | 2xl |

### Tailwind breakpoints:

| Breakpoint | Description |
| -------- | ---------- |
| < 640px | xs |
| >=640px | small |
| >=768px | medium |
| >=1024px | large |
| >=1280px | xl |
| >=1536px | 2xl |