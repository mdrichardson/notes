# Callbacks

*Note: Old. Prefer using Async/Await over Callbacks*

Given:

```js
const posts = [
    {title: 'Post One', body: 'This is post one'},
    {title: 'Post Two', body: 'This is post two'},
]
```

We need to asynchronously fetch the posts from a server. Without callbacks, we could use:

```js
getPosts = () => {
    // We use setTimout to pause the script until we think it has fetched the data we want
    setTimeout(() => {
        let output = '';
        posts.forEach((post) => {
            output += `<li>${post.title}</li>`;
        });
        document.body.innerHTML = output;
    }. 1000)
}

createPost = (post) => {
    setTimeout(() => {
        posts.push(post);
    }, 2000);
}
```

The problem with this is that the DOM already gets painted before `createPost()` is called. So `createPost()` basically becomes useless. Instead, we could make a callback.

```js
getPosts = () => {
    // We use setTimout to pause the script until we think it has fetched the data we want
    setTimeout(() => {
        let output = '';
        posts.forEach((post) => {
            output += `<li>${post.title}</li>`;
        });
        document.body.innerHTML = output;
    }. 1000)
}

createPost = (post, callback) => {
    setTimeout(() => {
        posts.push(post);
        // callback() forces it to wait until the function is complete
        callback();
    }, 2000);
}
```

In order to use the callback, you would call it like:

```js
createPost({title: 'Post Three', body: 'This is post three' }, getPosts);
```