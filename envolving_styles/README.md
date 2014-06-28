# Envolving styles

Sometimes you want to ship some stylesheets long with the scripts.

By defining the `css` field in `cortex.json`, you can specify where your css resources lies in. All files matching the pattern will be packaged into the bundle.

```
{
  "css": [
    "css/*.css"
  ]
}
```

If you are using some css preproccessors such as stylus, you can specified the prebuild process by setting the `scripts` field in cortex.json, when running `cortex build`, the prebuild script will be run first, then the built result(here we build the css files into built_css) will be packaged in to the bundle.

```
{
  "scripts": {
    "prebuild": [
      "gulp stylus"
    ]
  },
  "css": [
    "built_css/*.css"
  ]
}
```
