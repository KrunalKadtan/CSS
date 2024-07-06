# Animations

Animation in CSS allows you to animate the properties of HTML elements without needing JavaScript or Flash. CSS animations are created using keyframes, which define the styles at various points in the animation timeline.

1. **Keyframes** : Define what the animation looks like at different points during the animation sequence.
2. **Animation Properties** : Apply the animation to an element and define how it behaves.

### Basic Structure

1. **Define Keyframes** : Use the `@keyframes` rule to create keyframes.
2. **Apply the Animation** : Use the `animation` property to apply the animation to an element.

### Example

Basic example that animates a square from left to right:

**HTML**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Animation Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="animated-square"></div>
</body>
</html>
```

**CSS (styles.css)**
```css
.animated-square {
    width: 100px;
    height: 100px;
    background-color: blue;
    position: relative;
    animation: moveRight 2s infinite alternate;
}

@keyframes moveRight {
    0% {
        left: 0;
    }
    100% {
        left: 200px;
    }
}
```

### Explanation

1. **`.animated-square`** : This class applies initial styles to the square element, including its size, color, and position.
2. **`animation: moveRight 2s infinite alternate;`** : This property applies the animation to the element. 
   - `moveRight` is the name of the animation (defined with `@keyframes`).
   - `2s` sets the duration of the animation to 2 seconds.
   - `infinite` makes the animation repeat indefinitely.
   - `alternate` makes the animation alternate direction on each iteration.
3. **`@keyframes moveRight`** : Defines the keyframes for the `moveRight` animation.
   - `0%` represents the start of the animation (left: 0).
   - `100%` represents the end of the animation (left: 200px).

### More Properties

You can control various aspects of the animation using additional properties:

- `animation-delay` : Delay before the animation starts.
- `animation-iteration-count` : Number of times the animation should run.
- `animation-direction` : Direction of the animation (normal, reverse, alternate).
- `animation-timing-function` : Speed curve of the animation (linear, ease, ease-in, ease-out, ease-in-out).

### Example with More Properties

```css
.animated-square {
    width: 100px;
    height: 100px;
    background-color: blue;
    position: relative;
    animation: moveRight 2s ease-in-out 1s 3 alternate;
}

@keyframes moveRight {
    0% {
        left: 0;
    }
    100% {
        left: 200px;
    }
}
```

- `ease-in-out` : The animation will start slowly, speed up, and then slow down.
- `1s` : The animation will start after a 1-second delay.
- `3` : The animation will run 3 times.

# Transformations

- The `transform` property is used to apply a variety of transformations to an element, such as translating (moving), rotating, scaling, and skewing. When combined with CSS animations, `transform` can create powerful and dynamic effects.

### Basic Transform Functions

1. **translate()** : Moves an element from its current position.
2. **rotate()** : Rotates an element around a fixed point.
3. **scale()** : Scales an element up or down.
4. **skew()** : Skews an element along the X and Y axes.

### Example Using `transform`

**HTML**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Transform Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="animated-box"></div>
</body>
</html>
```

**CSS (styles.css)**
```css
.animated-box {
    width: 100px;
    height: 100px;
    background-color: blue;
    position: relative;
    animation: transformExample 4s infinite;
}

@keyframes transformExample {
    0% {
        transform: translate(0, 0) rotate(0deg) scale(1) skew(0deg, 0deg);
    }
    25% {
        transform: translate(100px, 0) rotate(45deg) scale(1.2) skew(10deg, 10deg);
    }
    50% {
        transform: translate(100px, 100px) rotate(90deg) scale(1.5) skew(20deg, 20deg);
    }
    75% {
        transform: translate(0, 100px) rotate(135deg) scale(1.2) skew(10deg, 10deg);
    }
    100% {
        transform: translate(0, 0) rotate(180deg) scale(1) skew(0deg, 0deg);
    }
}
```

### Explanation

1. **`.animated-box`** : This class applies initial styles to the box element, including its size, color, and position.
2. **`animation: transformExample 4s infinite;`** : This property applies the animation to the element.
   - `transformExample` is the name of the animation (defined with `@keyframes`).
   - `4s` sets the duration of the animation to 4 seconds.
   - `infinite` makes the animation repeat indefinitely.
3. **`@keyframes transformExample`** : Defines the keyframes for the `transformExample` animation.
   - `0%` : The element starts in its original position with no transformation.
   - `25%` : The element moves 100px to the right, rotates 45 degrees, scales up to 1.2 times its original size, and skews 10 degrees along both axes.
   - `50%` : The element moves diagonally 100px down, rotates 90 degrees, scales up to 1.5 times its original size, and skews 20 degrees along both axes.
   - `75%` : The element moves 100px down, rotates 135 degrees, scales back down to 1.2 times its original size, and skews 10 degrees along both axes.
   - `100%` : The element returns to its original position, rotated 180 degrees, with no scaling or skewing.

### Combining `transform` with Other Properties

You can combine `transform` with other CSS properties for more complex animations.

```css
.animated-box {
    width: 100px;
    height: 100px;
    background-color: blue;
    position: relative;
    animation: transformAndOpacity 4s infinite;
}

@keyframes transformAndOpacity {
    0% {
        transform: translate(0, 0) rotate(0deg) scale(1);
        opacity: 1;
    }
    50% {
        transform: translate(100px, 100px) rotate(180deg) scale(0.5);
        opacity: 0.5;
    }
    100% {
        transform: translate(0, 0) rotate(360deg) scale(1);
        opacity: 1;
    }
}
```

### Explanation

- **`opacity`** : Changes the opacity of the element from fully visible (1) to half visible (0.5) and back to fully visible (1).

# Transitions

- The `transition` property allows you to change property values smoothly (over a given duration). It's useful for creating simple animations that occur when an element's state changes, such as when a user hovers over an element or clicks it.

### Basic Structure

The `transition` property is shorthand for several transition-related properties :
- `transition-property` : The name of the CSS property you want to animate.
- `transition-duration` : How long the transition should take.
- `transition-timing-function` : The speed curve of the transition.
- `transition-delay` : When the transition should start.

### Example

A simple example of a button changing color on hover :

**HTML**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Transition Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <button class="transition-button">Hover Me!</button>
</body>
</html>
```

**CSS (styles.css)**
```css
.transition-button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: blue;
    color: white;
    border: none;
    cursor: pointer;
    transition: background-color 0.5s ease, transform 0.5s ease;
}

.transition-button:hover {
    background-color: red;
    transform: scale(1.1);
}
```

### Explanation

1. **`.transition-button`** : This class applies initial styles to the button, including padding, font size, background color, text color, border, and cursor.
2. **`transition: background-color 0.5s ease, transform 0.5s ease;`** : This property applies the transition effects to the `background-color` and `transform` properties:
   - `background-color 0.5s ease` : The background color will change over 0.5 seconds with an `ease` timing function.
   - `transform 0.5s ease` : The transform property will change over 0.5 seconds with an `ease` timing function.
3. **`.transition-button:hover`** : This class changes the button's styles when it is hovered over:
   - `background-color: red;` : The background color changes to red.
   - `transform: scale(1.1);` : The button scales up by 10%.

### Transition Timing Functions

The `transition-timing-function` property can take several values to control the speed curve :
- `linear` : The transition has the same speed from start to end.
- `ease` : The transition starts slowly, accelerates in the middle, and slows down at the end (default).
- `ease-in` : The transition starts slowly.
- `ease-out` : The transition ends slowly.
- `ease-in-out` : The transition starts and ends slowly.
- `cubic-bezier(n, n, n, n)` : Defines a custom speed curve.

### Multiple Transitions

You can animate multiple properties at once by listing them in the `transition` property, separated by commas:

```css
.transition-button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: blue;
    color: white;
    border: none;
    cursor: pointer;
    transition: background-color 0.5s ease, transform 0.5s ease, color 1s linear;
}

.transition-button:hover {
    background-color: red;
    transform: scale(1.1);
    color: yellow;
}
```

- `background-color` and `transform` transitions last 0.5 seconds with an `ease` timing function.
- `color` transition lasts 1 second with a `linear` timing function.

### Delay

You can also add a delay before the transition starts using `transition-delay`:

```css
.transition-button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: blue;
    color: white;
    border: none;
    cursor: pointer;
    transition: background-color 0.5s ease 0.2s, transform 0.5s ease 0.2s;
}

.transition-button:hover {
    background-color: red;
    transform: scale(1.1);
}
```

In this example, both transitions will start after a 0.2-second delay.