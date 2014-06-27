# Write code as nodejs

Now let's get hand dirty.

## 1. Initialze the project

First make a directory called 'colorify', in the direcory root path, run:

```
cortex init
```

Cortex will ask you a bunch of questions, and using the default will be fine. If everything goes well, you will find the project structure like this:

```
colorify
|-test              // your test cases belongs here
|   |colorify.js
|-cortex.json       // package info, similar to package.json in npm
|-index.html        // module runner
|-index.js          // module's entry point
```

## 2. Install dependencies

We need to set the background color of a dom element, so let `jquery` helps us to do so. Install jquery by:

```
cortex install --save jquery
```

Cortex will download all the dependencies into a folder called 'neuron', and You will see the console output:

```
installing assert@*
   GET http://r.ctx.io/assert 200
   GET http://r.ctx.io/json 200
   GET http://registry.cortex.dp/json/-/json-1.0.1.tgz 200
   GET http://r.ctx.io/util 200
   GET http://registry.cortex.dp/util/-/util-1.0.4.tgz 200
   GET http://r.ctx.io/assert/-/assert-1.0.1.tgz 200
write /Users/ltebean/Desktop/colorify/neurons/assert/1.0.1/assert.js
write /Users/ltebean/Desktop/colorify/neurons/json/1.0.1/json.js
write /Users/ltebean/Desktop/colorify/neurons/util/1.0.4/util.js
```

## 3. Writing code

Now that `jquery` is installed, we can depend on it to reach our goal, edit index.js:

```js
var $ = require('jquery');

function colorify(selector,color){
	$(selector).css('background-color',color)
}

module.exports = colorify;
```

Our work is done! and you will find that we write code just the same way as in Node.js






