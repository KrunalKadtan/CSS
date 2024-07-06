# Organization

- Modifiers typically refer to classes or other attributes that alter the appearance or behavior of elements.
- Modifiers are often used in conjunction with the BEM (Block, Element, Modifier) methodology, but they can be applied in various ways in any CSS structure.

### BEM Methodology

BEM is a naming convention for classes in HTML and CSS to help keep code maintainable and clear.

- **Block** : The main container (e.g., `.button`).
- **Element** : A part of the block that performs a specific function (e.g., `.button__icon`).
- **Modifier** : A variant or state of the block or element (e.g., `.button--large`).

### Example Using BEM

**HTML**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BEM Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <button class="button button--large">
        <span class="button__icon">👍</span>
        Like
    </button>
</body>
</html>
```

**CSS (styles.css)**
```css
/* Block */
.button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: blue;
    color: white;
    border: none;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
}

/* Element */
.button__icon {
    margin-right: 8px;
}

/* Modifier */
.button--large {
    padding: 15px 30px;
    font-size: 20px;
}
```

### Explanation

1. **`.button`** : This is the block class for the button.
2. **`.button__icon`** : This is the element class for the icon within the button.
3. **`.button--large`** : This is the modifier class that changes the size of the button.

### Using Modifiers in CSS

You don't have to follow BEM strictly. You can use modifiers to create different states or versions of an element in various ways :

**HTML**
```html
<button class="btn btn-primary">Primary Button</button>
<button class="btn btn-secondary">Secondary Button</button>
```

**CSS (styles.css)**
```css
/* Base button styles */
.btn {
    padding: 10px 20px;
    font-size: 16px;
    border: none;
    cursor: pointer;
}

/* Modifier for primary button */
.btn-primary {
    background-color: blue;
    color: white;
}

/* Modifier for secondary button */
.btn-secondary {
    background-color: gray;
    color: white;
}
```

### Explanation

1. **`.btn`** : This is the base class for buttons.
2. **`.btn-primary`** : This modifier class applies styles for a primary button.
3. **`.btn-secondary`** : This modifier class applies styles for a secondary button.

### State Modifiers

Modifiers are also useful for different states of an element, such as active, disabled, or hovered states:

**HTML**
```html
<button class="btn btn-primary btn--disabled" disabled>Disabled Button</button>
```

**CSS (styles.css)**
```css
/* Base button styles */
.btn {
    padding: 10px 20px;
    font-size: 16px;
    border: none;
    cursor: pointer;
}

/* Modifier for primary button */
.btn-primary {
    background-color: blue;
    color: white;
}

/* Modifier for disabled state */
.btn--disabled {
    background-color: lightgray;
    color: darkgray;
    cursor: not-allowed;
    opacity: 0.6;
}
```

### Explanation

- **`.btn--disabled`** : This modifier class applies styles for a disabled button state.