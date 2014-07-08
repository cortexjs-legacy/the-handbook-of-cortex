# cortex-scripts

Cortex support:

* prebuild: run before `cortex build`.
* prepublish: run before the package is packed to tarball to publish.
* preinstall run before the package is installed. When the package is donwloaded and the tarball is unpacked, the script will be run.


## Use Cases

Suppose:

1. You use a css preprocessor like stylus and you want convert .styl files to .css files before built.
2. The task is run by `gulp`.

You can define the scripts field as follows:

```js
{
  "scripts": {
    "prebuild": "gulp"
  }
}
```
