# Cortex v.s.

First of all, cortex is a project in production of large websites for over 1 years, not a project which only has specifications and people just watch, wait and see.

Then, cortex might have the most exquisite version control ability over other browser-side solutions so far, making us free from worry to to collaborate with each others.

## Cortex vs. Requirejs/systemjs

#### Cortex is A Package Manager
Requirejs or systemjs is a **module loader**, while Cortex a is package manager.

A package could have many modules and only one entrypoint (which let out the APIs of the package). And a package for browsers could also contain csses, images, fonts, etc.

Cortex helps to write modules arbitrarily and provides a way to make the granularity under a rational level.

#### Forget *MDs

> Anyone who actually enjoys writing module systems is too insane to be trusted. The only rational position is to do the simplest necessary thing, and as quickly as possible get to the business of building real programs with it. Optimize for that.
> -- Isaac Z. Schlueter, the author of NPM

There are too many *MDs in the world, forget them, just follows [module/1.0](http://wiki.commonjs.org/wiki/Modules/1.0) standard and write code in the Node way.

With requirejs/systemjs, you have to wrap your code with `define.amd`, while with Cortex, you write code the same way as in Node.js. Cortex will handle everything you need to make the code work in browser.

Actually, AMD or something is hard to cover all cases, such as SemVer ranges, and fallback of [file modules](http://nodejs.org/api/modules.html#modules_file_modules).

Leave the code with only module/1.0, so you need not to change anything to embrace the future.


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

Browserify is pretty lovely and nice (and James is an interesting guy ;D), but the main differences between Cortex and Browserify are:

- Cortex is not only suitable for small projects,  but also scale well for enterprise projects.

- Cortex will not bundle all the things into a single file.

- Browserify aims to make node modules work in the browser, while Cortex is build for the web, it uses its own registry, which leads to no ambiguity about whether a package is browser-compatible.


## Cortex vs. Bower

Bower does not actually make the package modular, because JavaScript files downloaded by Bower interact with each other by global variables of the same scope, which, is not good for distributed workflows with lots of developers.

And since bower just downloads and leaves, you have to manually coordinate JavaScript files and import the JavaScript or css files into the html one by one.

Cortex manages each module in an isolated sandbox, which allows multiple versions of the same dependency exist simultaneously while Bower can not, due to the reason described above.


## Cortex vs. Webpack

Webpack does a great work, although cortex and webpack are doing different things.

> We don't like too many choices in front of us.
>
> We just want to get things done.

We encourage people to make the browser-side projects clean, with

- basic configurations,
- better declaration of dependencies,
- only node-style modules (which is good for the ecosystem in many ways)

to improve the ecosystem for browsers just like NPM does for nodejs, helping people make useful packages.

Cortex is much like NPM, so if you are familiar with nodejs development, you are already know how to make things work on browsers, and it will only takes a few seconds to make a hello world package, with cortex.

Cortex has a workflow for developers to care less and do more, and focuses on the primary actions for a developer to make a product come true, and better experiences to collaborate with multiple developers. We've been building massive applications, that we know the pain.


