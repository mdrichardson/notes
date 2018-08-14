# JavaScript Closures

It's always good to isolate against global variables by using closures (unless you're using something like `webpack` that adds them automatically).

Simple way:

```javascript
(() => {

    // Code you want enclosed

})()
```

The `()` at the end makes it self-execute