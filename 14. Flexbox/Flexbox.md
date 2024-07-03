# Flexbox

- Flexbox, or the Flexible Box Layout, is a CSS layout model that allows you to design a flexible and responsive layout structure without using float or positioning.

## Flex Container

- First, define a flex container by setting the display property to `flex`.

```css
.container {
  display: flex;
}
```

## Flex Items

- The direct children of the flex container automatically become flex items.

```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

## Flexbox Properties

**1. Container Properties :**

- `flex-direction` : Defines the direction of the flex items. **Possible values :** row, row-reverse, column, column-reverse.
- `justify-content` : Aligns the flex items along the main axis. **Possible values :** flex-start, flex-end, center, space-between, space-around, space-evenly.
- `align-items` : Aligns the flex items along the cross axis. **Possible values :** flex-start, flex-end, center, baseline, stretch.
- `flex-wrap` : Determines whether flex items should wrap or not. **Possible values :** nowrap, wrap, wrap-reverse

**2. Item Properties :**

- `order` : Specifies the order of the flex items. Default is 0.
- `flex-grow` : Defines the ability for a flex item to grow if necessary. Default is 0.
- `flex-shrink` : Defines the ability for a flex item to shrink if necessary. Default is 1.
- `flex-basis` : Defines the default size of an element before the remaining space is distributed.
- `align-self` : Allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.

## Example

```html
    <main class="container">
        <div class="box">1</div>
        <div class="box">2</div>
        <div class="box">3</div>
        <div class="box">4</div>
        <div class="box">5</div>
        <div class="box">6</div>
   </main>
```

```css
.container {
  max-width: 800px;
  min-height: 400px;
  margin-inline: auto;
  border: 1px solid #000;
  display: flex;
  gap: 1rem;
  justify-content: center;
  align-items: center;
  flex-flow: row wrap;
  align-content: space-evenly;
} 

.box {
  /* min-width: 100px; */
  height: 100px;
  background-color: #000;
  color: #fff;
  font-size: 2rem;
  padding: 0.5rem;

  display: flex;
  justify-content: center; 
  align-items: center;

  flex: 1 1 150px;
}

.box:nth-child(2) {
  flex: 2 2 150px;
  order: 1;
}
```

- `max-width` sets the maximum width an element can be. Useful for ensuring that an element does not grow beyond a certain size, even if its content or parent allows for more space.

- `max-height` sets the maximum height an element can be. Ensures that an element does not grow taller than a specified value, which is useful for controlling layout and overflow.

- `min-width` sets the minimum width an element can be. Ensure that an element does not shrink below a specified width.

- `min-height` set the minimum height an element can be. Enssure that an element does not shrink below a specified height.

- The height adjusts automatically based on the content as long as it stays within the min and max constraints.

- `flex-flow` is a shorthand property to set both the `flex-direction` and `flex-wrap` properties in one line.

- `align-content` is used in Flexbox and Grid layouts. It adjusts the spacing between rows or columns of flex items within a flex container, affecting only when there is extra space in the cross-axis.
- Values for `align-content` :
    1. `stretch` (default) : Stretches the rows to take up the remaining space.
    2. `center` : Packs the rows in the center of the container.
    3. `flex-start` : Packs the rows at the start of the container.
    4. `flex-end` : Packs the rows at the end of the container.
    5. `space-between` : Distributes the rows evenly, with the first row at the start and the last row at the end.
    6. `space-around` : Distributes the rows evenly with equal space around them.
    7. `space-evenly` : Distributes the rows with equal space between them.

- `flex` is a shorthand for the three properties `flex-grow`, `flex-shrink`, and `flex-basis` combined. It is used to define how a flex item will grow, shrink, and how much space it will take up within a flex container.

#

Practice Flexbox here : https://flexboxfroggy.com/