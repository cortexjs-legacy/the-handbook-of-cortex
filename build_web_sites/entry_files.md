# Entry files

Unlike module(which has a single entry),  a website usually consists of lots of pages, which results in mutiple entry files.

To define entry files, edit `cortex.json` 's `entries` field:

```
"entries": [
    "entries/index.js",
    "entries/shop.js"
 ]
```

glob pattern is also supported:

```
"entries": [
    "entries/*.js"
 ]
```

All the matching files will be built to the destination when you run `cortex build`.


