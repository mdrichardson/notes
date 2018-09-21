# Using @supports as a Last Resort

If you still can't get things working in IE, you can use `@supports` in your CSS. For example, IE doesn't support `mask-image`, so you can:

```css
@supports (mask-image: url(URL)) {
    mask-image: url(URL);
    background: red;
}

@ supports not (mask-image: url(URL)) {
    background: yellow;
}
```