# Styling Links

- Styling the hypertext link is the extention of Typography.
- The default stylings for hypertext link are font color is blue before visiting the link, font color is purple after visiting the link, if we click & hold on the link its font color is orange, it has underlined text, etc.

```css
a {
    text-decoration: none;
    cursor: pointer;
    color: blue;
}

a:visited {
    color: blueviolet;
}

a:hover, a:focus {
    color: dodgerblue;
}

a:active {
    color: red;
}
```

- `text-decoration` has value **none** which is use to remove underline.
- `cursor` has value **pointer** which is used to show pointer while cursor is on hypertext link.
- `color` inside `a:visited` is used to change color after visiting that link.
- `color` inside `a:hover` is used to change color while hovering over the hypertext link.
- `color` inside `a:active` is used to change color while holding the hypertext link.
- `a:focus` is used to targets an element that is currently focused by the user.