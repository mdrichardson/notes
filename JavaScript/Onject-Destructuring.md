# Destructuring JavaScript Objects

If we have object:

```js
var animal = {
    name: 'bob',
    meal: 10,
    diet: 'berries'
}
```

Instead of:

```js
function feed(animal) {
    return `Feed ${animal.name} ${animal.meal} pounds of ${animal.diet}`
}
```

We can save typing "animal" a bunch of times with:

```js
function feed({ name, meal, diet }) {
    return `Feed ${name} ${meal} pounds of ${diet}`
}
```

Or:

```js
function feed(animal) {
    const { name, meal, diet } = animal;
    return `Feed ${name} ${meal} pounds of ${diet}`
}
```