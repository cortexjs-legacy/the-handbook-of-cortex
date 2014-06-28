# Bootstrap with facades

Cortex uses neuron as the module loader, first include these two scripts in the page from the built result:

* neuron.js - the module loader
* config.js - dependency version config

Then config the module root path, suppose you place all the modules on '/public/build/neurons':

```
neuron.config({
    path: '/public/build/neurons'
});
```

Finally you can load the entry file by:

```
facade({
    mod:'{packageName}/{pathToTheEntryFile}'
})
```

For example, on the item detail page, load the script by:
```
facade({
    mod:'flower-shop/entries/item-detail.js'
})
```
