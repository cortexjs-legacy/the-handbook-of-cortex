# How to Write a Cortex Plugin

Cortex is using the linux command system to manage plugins.

Actually, it is quite simple to write a cortex plugin.

## Create a Node.js Project with Bin

Creates an empty project:

```bash
$ npm init
```

And specify the `bin` field of package.json

```js
{
  "bin": {
    "cortex-myplugin": "bin/my-plugin.js"
  }
}
```

Then complete the `bin/my-plugin.js` as a normal node.js command line program:

```js
#!/usr/bin/env node

console.log('Hello World!\n');
console.log('And the `argv` is', process.argv);
```

## `npm link` to Run

```bash
$ npm link
$ cortex myplugin --haha
> Hello World!
> And the `argv` is, ['xxxx', 'myplugin', '--haha']
```

## Other Useful Stuffs

You can use several nice module to handle the argument vector, such as [`minimist`](http://www.npmjs.org/package/minimist) by @substack.

And there are lots of utility modules which are used by cortex, you can find them in the group [github/cortexjs](https://github.com/cortexjs) or by searching `'cortex'` in [npmjs.org](https://www.npmjs.org/search?q=cortex).

## Something You Need to Know

- You can not use a name of the built-in command of cortex, such as `cortex-install`, it won't work.
