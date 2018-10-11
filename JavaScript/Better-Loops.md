# Coding Better Loops

Instead of:

```js
const total = 0;
const withTax = [];
const highValue = [];
for (i = 0; i < orders.length; i++) {

    // Reduce
    total += orders[i];

    // Map
    withTax.push(orders[i] * 1.1);

    // Filter
    if (orders[i] > 100 {
        highValue.push(orders[i]);
    })
}
```

We could use:

```js
const total = orders.reduce((accumulated, current) => accumulated + current)

const withTax = orders.map(v => v * 1.1)

const highValue = orders.filter(v => v > 100);
```