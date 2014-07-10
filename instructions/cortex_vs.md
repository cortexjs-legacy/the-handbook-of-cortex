# Cortex v.s.

## Cortex vs. Component

Component uses Github as its registry, although Github is so fancy that all our developers like it so much, it  results in inadequate constraints and check to ensure a package is just ready for use.

We hope that all packages should be built and verified before publish. When you install a package, all the things is just ready for use and you don’t need to care about whether the package needs an additional build step, because all theses things are done before it is published.

Distributed system is benefit to the growth of an ecosystem, however, certain controls and constraints will help it grow more healthily.

Second, using github's `<user>/<repo>` namespace results in many forked versions of the same package, which we don't want it to be, potentially. Also, `<user>/<repo>` does not solve naming confliction, so we do not do this. @izs has a better solution using [scoped package names](https://github.com/npm/npm/issues/5239).


Another major difference is that Cortex will not bundle all the things into a single file, this bring us lots of benefits:
- Allows flexible combo strategy to increase hit rate on CDN.
- Makes it possible to automatically pack a package and its dependencies into a zip file for delivery or download purpose.
- Other creative ideas that only limited by your imagination.

Then, `component.remotes` and `component.paths` are configs for environment which are confusing and should not be included in the project. Cortex uses profiles to manage this kind of configurations like Google Chrome.

Finally, we have a professional team working on cortex. It is **OK** even if one of our developers says farewell because we are not only one person. And a bunch of projects are using cortex, so cortex will be continueously maintained.

## Cortex vs. Browserify

Browserify is pretty lovely and nice, but the main differences between Cortex and Browserify are:

- Cortex is not only suitable for small projects,  but also scale well for enterprise projects.

- Cortex will not bundle all the things into a single file.

- Browserify aims to make node modules work in the browser, while Cortex is build for the web, it uses its own registry, which leads to no ambiguity about whether a package is browser-compatible.


## Cortex vs. Bower

Bower does not actually make the package modular, because JavaScript files downloaded by Bower interact with each other by global variables of the same scope, which, is not good for distributed workflows with lots of developers.

And since bower just downloads and leaves, you have to manually coordinate JavaScript files and import the JavaScript or css files into the html one by one.

Cortex manages each module in an isolated sandbox, which allows multiple versions of the same dependency exist simultaneously while Bower can not, due to the reason described above.

## Cortex vs. Requirejs

Requirejs is a module loader, while Cortex a is package manager.

> Anyone who actually enjoys writing module systems is too insane to be trusted. The only rational position is to do the simplest necessary thing, and as quickly as possible get to the business of building real programs with it. Optimize for that.
> -- Isaac Z. Schlueter, the author of NPM

With requirejs, you have to wrap your code with `define.amd`, while with Cortex, you write code the same way as in Node.js. Cortex will handle everything you need to make the code work in browser.

It’s always better to make our source code clean, just follows [module/1.0](http://wiki.commonjs.org/wiki/Modules/1.0) standard and write code in the Node way.





