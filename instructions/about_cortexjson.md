# About cortex.json

Most of the fields in cortex.json is similar to `npm`'s package.json.

It is important to know the meaning of each field.

## name

This is the most important field, it specifies the package name, which is the unique identifier of a package.

## version

The version of the package. Changes to the package should always come along with changes to the version.

## description

It helps people to know what is this package about.

## keywords

It's an array of strings, always put some keywords here, and it will helps people to discover the package while searching


## main
The entry point of a package, it's modules.exports will be returned when calling `require(packageName)`.

## entries
Cotex supports multiple entries(See Chapter 4.1 for details). All matching files will be treated as an entry when built, and you can load them using `facade` or `require.async`

Usage:
```
{
  "entries": [
    "entries/*.js",
    "pages/a.js"
  ]
}
```

## css
This field specifies where are the css resources. It's an array of file path, glob pattern is also supported. The order matters and it decides the built result.
```
{
  "css": [
    "css/a.css",
    "css/b.css"
   ]
}
```

## directories.src

Describe resources such as images, templates. Suppose you place them in a folder called `'source'`:
```
root/
   |-- source/
            |-- avatar.png
   |-- index.js
```


set the `direcotries.src` field to that folder:
```
{
  "directories": {
    "src": "source"
  }
}
```

Then in index.js, you can use require.resolve() to accquire the absoulute path of that resources.
```js
var default_avatar = require.resolve('./source/avatar.png');
```

## scripts

Allows you to define custom build scripts during the life cycle of the package. For detailed reference see the next chapter.










