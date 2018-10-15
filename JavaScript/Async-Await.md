# Async/Await

Async/Await is like a new, cleaner version of Callbacks and Promises.

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

Relative to the Callbacks and Promises examples, to call `createPost`, we can just use:

```js
async function init() {
    await createPost({ title: 'Post Three', body: 'This is post three' });
    getPosts();
}

init();
```