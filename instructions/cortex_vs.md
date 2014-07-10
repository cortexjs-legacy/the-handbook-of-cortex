# Cortex v.s.

## Cortex vs. Component

Component uses Github as its registry, although Github is so fancy that all our developers like it so much, it  results in inadequate constraints and check to ensure a package is just ready for use.

We hope that all packages should be built and verified before publish. When you install a package, all the things is just ready for use and you don’t need to care about whether the package needs an additional build step, because all theses things are done before it is published.

Distributed system is benefit to the growth of an ecosystem, however, certain controls and constraints will help it grow more healthily.

Second, using github's `<user>/<repo>` namespace results in many forked versions of the same package, which we don't want it to be, potentially. Also, `<user>/<repo>` does not solve naming confliction, so we do not do this. @izs has a better solution using [scoped package names](https://github.com/npm/npm/issues/5239).


Another major difference is that Cortex will not bundle all the things into a single file, this bring us lots of benefits:
- Allows flexible combo strategy to increase hit rate on CDN
- Makes it possible to package a module into zip for delivery or download purpose
- Other creative ideas that only limited by your imagination

Finally, there is no confuse with configurations for environment and projects in Cortex.

## Cortex vs. Browserify

Browserify is pretty lovely and nice, but the main differences between Cortex and Browserify are:

- Cortex is not only suitable for small projects,  but also scale well for enterprise projects.

- Cortex will not bundle all the things into a single file.

- Browserify aims to make node modules work in the browser, while Cortex is build for the web, it uses its own registry, which leads to no ambiguity about whether a package is browser-compatible.


## Cortex vs. Bower

Bower does not actually make the package modular. You have to import the JavaScript or css file downloaded by Bower manually.

And since there’s no constraints on what kind of module system(globals, plugins, AMD, and CommonJS) the package use, you have to coordinate JavaScript files by hand and it’s very difficult to integrated these files in a large project.


Meanwhile, Cortex allows multiple versions of the same dependency exist simultaneously while Bower can not.

## Cortex vs. Requirejs

Requirejs is a module loader, while Cortex a is package manager.

> Anyone who actually enjoys writing module systems is too insane to be trusted. The only rational position is to do the simplest necessary thing, and as quickly as possible get to the business of building real programs with it. Optimize for that.
> -- Isaac Z. Schlueter, the author of NPM

With requirejs, you have to wrap your code with `define.amd`, while with Cortex, you write code the same way as in Node.js. Cortex will handle all things to make your code work in browser.

It’s always better to make our source code clean, just follows [module/1.0](http://wiki.commonjs.org/wiki/Modules/1.0) standard and write code in the Node.js way.





