# Polyfills

To use EventSource in IE:

`import 'eventsource-polyfill'; // Need to remove "'Cache-Control': 'no-cache'," in eventsource.js`

In Angular, to fix "TypeError: Object doesn't support property or method 'matches'" in IE:

```
if (!Element.prototype.matches) {
    Element.prototype.matches = Element.prototype.msMatchesSelector;
  }
```