# cortex-scripts

This article describes how cortex handles the `scripts` field.

Cortex support:

* prebuild: run before `cortex build`.
* prepublish: run before the package is packed to tarball to publish. If `prepublish` is not defined, cortex will try to run `prebuild` instead. You can set `prepublish` as `''` to explicitly tell cortex to do nothing.
* preinstall run before the package is installed. When the package is donwloaded and the tarball is unpacked, the script will be run.

> **BUT, `scripts.preinstall` is an ANTIPATTERN**.

There is an [article](https://www.npmjs.org/doc/misc/npm-scripts.html#note-install-scripts-are-an-antipattern) by @izs about this.

## Use Cases

Suppose:

1. You use a css preprocessor like stylus and you want convert `.styl` files to `.css` files before built.
2. The task is handled by `gulp`.

You can define the scripts field as follows:

```js
{
  "scripts": {
    "prebuild": "./node_modules/.bin/gulp"
  }
}
```

Always remember to pre-build your inter-process codes, such as coffee-script, stylus, less, sass and etc, before publishing.

## Why

- Running the tasks builder beforehand makes sure that your package is already able to be used when users download it.

- Build scripts might depend on the operating system and the environment of your local machine, just like `make` or something. Maybe your user is a newbie who is using Windows.

- cortex-scripts are useful with `cortex watch`. Take the example above, `cortex watch` will listen to the changes of your files and automatically execute `gulp` and `cortex build`.

> A single step makes the ecosystem better.
