# About cortex.json

Most of the fields in cortex.json is similar to `npm`'s package.json.

It is important to know the meaning of each field.

## name

This is the most important field, it specifies the package name, which is the unique identifier of a package.

name should contains and only contains characters `[a-z0-9-\.]` and should start with alphabet, end with alphabeta or number. In the registry, names are case-insensitve.

## version

The version of the package. Changes to the package should always come along with changes to the version.

Version must be parseable by [node-semver](https://github.com/isaacs/node-semver).

## description

It helps people to know what is this package about.

## keywords

It's an array of strings, always put some keywords here, and it will helps people to discover the package while searching.

## main
The entry point of a package, it's modules.exports will be returned when calling `require(packageName)`.


## entries
Cotex supports multiple entries(See Chapter 2.1 for details). All matching files will be treated as an entry when built, and you can load them using `facade` or `require.async`

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
This field specifies where is the css resources. It's an array of file path, glob pattern is also supported. The order matters and it decides the built result.
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

Allows you to define custom build scripts during the life cycle of the package. For detailed reference see [Chapter 7.2 cortex-scripts](./cortex-scripts.md)


## ignores

This field tells cortex to ignore those files when publishing your project to registry. It's an array of descriptions which follows the format in [guidline of gitignore](http://git-scm.com/docs/gitignore).

By default, cortex will read `.cortexignore` as ignore files, if `.cortexignore` does not exist, cortex will try `.gitignore`, `.npmignore` by order.


## dependencies

Dependencies are specified with a simple hash of package name to version range. The version range is a string which has one or more space-separated descriptors.

In most cases, you don't need to modify this field by hand; When you installs some packages via `cortex install --save`, cortex will add the installed packages into this field for you.

## devDependencies

If someone is planning on downloading and using your module in their program, they probably don't want or need to download and build the external test or documentation that you use during development. Those external test and documentation framework should go to devDependencies field. You can use `cortex install --save-dev` to save a dependency into `devDependencies` hash.


For example, a dependencies hash could be:

```
{
  "dependencies" :
  {
    "foo" : "1.0.0"
    , "bar" : "~1.2.0"
    , "baz" : "^1.0.2"
    , "boo" : "2.x"
    , "qux" : ">= 3.0.1"
    , "myo" : ">= 1.8.0 < 2.0.0"
    , "elf" : "*"
    , "thr" : "3.3.x"
  }
}
```


## asyncDependencies

This field defines the dependencies will loaded at runtime dynamically. So those packages won't be loaded until you use them.

Similar to above, you can modify this field via `cortex install --save-async`.


## license

You should specify a license for your package so that people know how they are permitted to use it, and any restrictions you're placing on it.


## Additional

If cortex can not find `cortex.json` in project folder, it will try to read `name`, `main`, `version` fields from package.json.
