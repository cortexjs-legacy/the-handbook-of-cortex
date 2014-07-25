# Entry Files

Unlike module(which has a single entry),  a website usually consists of lots of pages, which results in multiple entry files.

Suppose our website has 3 pages:
* index page
* item list page which display the search results
* item detail page

and thus results in 3 entries:
* index.js
* item-list.js
* item-detail.js

The project structure might look like this:

```
flower-shop
|-neurons       //  dependencies and built result
|-entries
|   |-index.js
|   |-item-list.js
|   |-item-detail.js
|-cortex.json
|-index.html
|-index.js
```

To load these entry files in the page, we need to define them as entries by editing `cortex.json` 's `entries` field:

```
"entries": [
    "entries/index.js",
    "entries/item-list.js"
    "entries/item-detail.js"
 ]
```

glob pattern is also supported:

```
"entries": [
    "entries/*.js"
 ]
```

All the matching files will be built to the destination when you run `cortex build`, and In the next chapter we will learn how to load them using `facade()`.


