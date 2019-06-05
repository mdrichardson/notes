# Classes

Call a class method without needing to construct a "new" class by making the method `static`:

```javascript
class Utility {
    static getStuff() { }
}

const stuff = Utility.getStuff();
```

