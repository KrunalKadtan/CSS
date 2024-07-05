# Variables

- CSS Variables, also known as Custom Properties, allow you to store values that you can reuse throughout your CSS.

#### Declaring and Using CSS Variables

1. **Declaring Variables**: You define a variable using the `--` prefix. Typically, variables are defined within the `:root` selector so they are available globally.

   ```css
   :root {
     --main-bg-color: #3498db;
     --main-text-color: #ffffff;
     --main-padding: 20px;
   }
   ```

2. **Using Variables**: You use the `var()` function to access the value of a variable.

   ```css
   body {
     background-color: var(--main-bg-color);
     color: var(--main-text-color);
     padding: var(--main-padding);
   }
   ```

#### Scope of Variables

- **Global Scope**: Defined in the `:root` selector, variables are available throughout the entire document.
- **Local Scope**: Defined within a specific selector, variables are only available within that selector and its descendants.

```css
:root {
  --global-color: blue;
}

.container {
  --local-padding: 10px;
}

.container .item {
  background-color: var(--global-color); /* Can access global variable */
  padding: var(--local-padding); /* Can access local variable */
}

.another-container {
  padding: var(--local-padding); /* Cannot access local variable from .container */
}
```

#### Fallback Values

You can provide a fallback value in case a variable is not defined.

```css
.element {
  color: var(--undefined-variable, black); /* Fallback to black if --undefined-variable is not set */
}
```


# `prefers-color-scheme` (Media Feature)

The `prefers-color-scheme` media feature is used to detect if the user has requested a light or dark color theme. This allows websites to automatically adapt their styles to match the user's system preference.

#### Values
- **`light`**: Indicates that the user prefers a light theme.
- **`dark`**: Indicates that the user prefers a dark theme.

### Using `prefers-color-scheme`

#### Example
Here's how you can use `prefers-color-scheme` to apply different styles based on the user's preferred color scheme:

```css
/* Default (light) theme */
body {
  background-color: white;
  color: black;
}

/* Dark theme */
@media (prefers-color-scheme: dark) {
  body {
    background-color: black;
    color: white;
  }
}
```

In this example, the default styles are for a light theme. If the user's system preference is set to dark mode, the styles within the `@media (prefers-color-scheme: dark)` block will be applied, changing the background to black and the text color to white.

#### Advanced Example with CSS Variables

You can combine `prefers-color-scheme` with CSS variables to make it easier to manage and switch between themes.

```css
:root {
  --background-color: white;
  --text-color: black;
}

@media (prefers-color-scheme: dark) {
  :root {
    --background-color: black;
    --text-color: white;
  }
}

body {
  background-color: var(--background-color);
  color: var(--text-color);
}
```

In this example, The `@media` query updates these variables based on the user's preferred color scheme.