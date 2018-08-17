# JavaScript Closures

It's always good to isolate against global variables by using closures (unless you're using something like `webpack` that adds them automatically).

Simple way:

```javascript
(() => {

    // Private code you want enclosed

    return {
        // public code you want shared
    }

})()
```

The `()` at the end makes it self-execute

Now, with ES6, we can use classes

```javascript
class xyz {

    constructor() {
        // private properties
    }

    // public methods

    doThis() {
        return 'abc'
    }
}

// Make it so we can use the class elsewhere
export default xys;
```