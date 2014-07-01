# Envolving Styles and Other Resources


## 1. Stylesheet
Sometimes you want to ship some stylesheets along with the scripts.

By defining the `css` field in `cortex.json`, you can specify where your css resources lies in. The order matters and glob pattern is supported. All files specified in this field will be packaged into the bundle.

```json
{
  "css": [
    "css/a.css",
    "css/b.css"
  ]
}
```

If you are using some css preproccessors such as stylus, you can specified the prebuild process by setting the `scripts` field in cortex.json, when running `cortex build`, the prebuild script will be run first, then the built result(here we build the css files into built_css) will be packaged in to the bundle.

```json
{
  "scripts": {
    "prebuild": [
      "gulp stylus"
    ]
  },
  "css": [
    "built_css/a.css",
    "built_css/a.css"
  ]
}
```



## 2. Ohter resources
You can also ship other resources such as images, templates. Suppose you place them in a folder called 'source':

```
root/
   |-- source/
            |-- avatar.png
   |-- index.js
```


In cortex.json, set the `direcotries.src` field to that folder:

```json
{
  "directories": {
    "src": "source"
  }
}
```

Then in index.js, you can use require.resolve() to accquire the absoulute path of that resources.

```js
var avatar_path = require.resolve('./source/avatar.png');
```
