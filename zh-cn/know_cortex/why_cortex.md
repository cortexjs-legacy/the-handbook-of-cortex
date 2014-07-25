# Cortex 的优势

> We **NEVER** make toys.

## 胜任企业级应用的高要求

Cortex has been used in production of [dianping.com](http://t.dianping.com) for years.

Dianping is the largest leading local life information and trading platform in China. And all our mobile websites and hybrid applications are using cortex.

We use cortex to help use to collaborate with developers from other teams and even different business units.

Cortex will seperate each JavaScript file into a unique sandbox scope, which means it is safe for several developers to collaborate with each others.

## If you use NPM, you already know how to use Cortex

## Accurate Version Control

- Allow multiple versions exist simultaneously.
- Full support for [SemVer](http://semver.org) and SemVer ranges
- No need to modify your code to update dependencies.
- The abilities to lock down dependencies for important businesses.

## Say No to *MDs

> Do the simplest necessary thing.
>
> Just in the node way.

* Write code the same way as in Node.js, just use `require`, `exports`, `module.exports`. No need to wrap the code to make it work. Just forget AMD, UMD, and *MDs.
* `cortex build` handles everything  to make your code work in browser
* `require()`ing a directory, `__dirname`, `__filename` are also supported according to [File Module](http://nodejs.org/api/modules.html#modules_file_modules)

## Package Manager, Not a Script Manager

- Not only download files, but also connect them and make them working together.
- Handle assets and you need not to write `<script>` tags for most of time.
- A package is a self-contained unit which is not just javascripts, it also contains css, images, fonts, and .etc.

## Pure Registry Cloud

* A registry cloud only for browsers. All the packages work in browsers, no ambiguity.
* Most of time, the intersection of server-side packages and browser-side packages is little and at low level. We need a better ecosystem to make it larger.
* Additional yet useful features are provided: package tagging, watching a project’s updates, and etc.

## Professional Dev Team Who DO Focus

> A pull request takes MONTHs to merge?
>
> Bugs with no replies?

You will never worry about that. Bugs have high priorities because we use it in production!

****

To compare with other managers, see [cortex v.s.](http://book.ctx.io/instructions/cortex_vs.html)

