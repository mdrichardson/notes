# NPM Run-Scripts

These are some good scripts to add to `package.json`

## Better `build` with `.htaccess` copying

If you use [this service worker fix](./Service-Worker-Fixes.md) and/or `.htaccess` and you want those implemented when `build`ing, you can use this to make it easy. This also adds some `build` arguments for a better-optimized `build`.

In `package.json`, add/change `"build:prod"`:

```json
"build:prod": "ng build --prod --build-optimizer --vendor-chunk && cp ./src/.htaccess ./dist${PROJECTNAME} && bash ./fix-sw.sh"
```

To run, use `npm run-script build:prod`

## Using `ng serve` with SSL

If you store your SSL certs in `./ssl`, you can `ng serve` with the certs included to test greenlock.

In `package.json`, change `"start"` to:

```json
"scripts": {
    ...
    "start": "ng serve -o --ssl true --ssl-cert ssl/server.crt --ssl-key ssl/server.key",
```

To run, use `npm run-script start`

## Using `ng build` with SSL

You can test service workers with SSL by building and then having http-server load it.

In `package.json`, add `"build:serve"`:

```json
"scripts": {
    ...
    "build:serve": "cp ./ssl/server.key ./dist/${PROJECTNAME} && cp ./ssl/server.crt ./dist/${PROJECTNAME} && cd ./dist/${PROJECTNAME} && http-server -p 4200 --cors='*' -c-1 --S -C server.crt -K server.key"
```

To run, use `npm run-script build:serve`