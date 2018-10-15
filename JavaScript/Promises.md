# Promises

*Note: Old. Prefer using Async/Await over Callbacks*

Given:

```js
const posts = [
    {title: 'Post One', body: 'This is post one'},
    {title: 'Post Two', body: 'This is post two'},
]
```

We need to asynchronously fetch the posts from a server. With Promises (vs. callbacks), we'd call it like:

```js
createPost = (post) => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            posts.push(post);
            const error = false;
            if(!error) {
                resolve();
            } else {
                reject('Error: Something went wrong!');
            }
    }, 2000);
    });
}
```

You don't need to pass in a callback with Promises. Instead, you would call it like:

```js
createPost({title: 'Post Three', body: 'This is post three' })
    .then(getPosts)
    .catch(err => console.log(err));
```

The primary benefit over callbacks is being able to use `resolve` and `reject`.

## Using Multiple Promises

We can use a lot of Pomises without having to use a bunch of `.then`. Example:

```js
const promise1 = Promise.resolve('Hello World');
const promise2 = 10;
const promise3 = new Promise((resolve, reject) =>
    setTimeout(resolve, 2000, 'Goodbye'));

Promise.all([promise1, promise2, promise3]).then((values) => console.log(values));
```

This gathers all of the Promises before console.logging them all together.