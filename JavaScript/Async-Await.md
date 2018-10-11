# Async/Await

Instead of:

```js
const sumRandomAsyncNums = () => {
    let first;
    let second;
    let third;

    return random()
        .then(v => {
            first = v;
            return random();
        })
        .then(v => {
            second = v;
            return random();
        })
        .then(v => {
            third = v;
            return random();
        })
}
```

We can just use:

```js
const sumRandomAsyncNums = async() => {
    const first = await random();
    const second = await random();
    const third = await random();

    console.log(`Result ${first + second +third}`);
}
```