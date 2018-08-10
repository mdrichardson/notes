# A Few Fixes for Service Workers

I was getting 504 "Gateway Timeout" errors because Angular's service worker was intercepting HTTP requests to an external API, when it should have ignored some. To fix:

To whitelist my API URLs, I opened `ngsw-worker.js` and changed `onFetch(event)` to:

```
onFetch(event) {
    const req = event.request;
    // List of words in request URL to whitelist/bypass the service worker
    const whitelist = ['api', 'otherWhitelistWords...']
    // Check to see if request url contains any whitelisted words and skip the rest of onFetch if it does
    if (whitelist.some(word => req.url.toLowerCase().includes(word.toLowerCase()))) {
                return
    }
    ...
}
```

You can automate fixing of `ng build:prod` by creating a `fix-sw.sh`:

```bash
#!/bin/bash
sed -i "/onFetch(event) {/,/const req = event.request;/c onFetch(event){const req=event.request;const whitelist=['api','otherWhitelistWords...'];if(whitelist.some(word=>req.url.toLowerCase().includes(word.toLowerCase()))){return}" ./dist/${PROJECTNAME}/ngsw-worker.js
```

To automate this change when building, in `package.json`, change your `build:prod` to:

```
"build:prod": "ng build --prod && bash ./fix-sw.sh",
```