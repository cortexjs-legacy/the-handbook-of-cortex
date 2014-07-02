# Write Code as Nodejs

Now let's get our hands dirty.

## 1. Initialze the Project

First make a directory called `'colorify'`, in the direcory root path, run:

```bash
cortex init
```

Cortex will ask you a bunch of questions, and using the default will be fine. If everything goes well, you will find the project structure like this:

```
colorify/
|-- test/              // your test cases belongs here
|      |-- colorify.js
|-- cortex.json        // package info, similar to package.json in npm
|-- index.html         // module runner
|-- index.js           // module's entry point
```

cortex.json is much like package.json in npm, it describes all the information about this package. For complete reference, see Chaptar 3.2 - About cortex.json.

## 2. Install Dependencies

We need to set the background color of a dom element, so let jquery helps us to do so. Install jquery by:

```bash
cortex install jquery --save
```

Cortex will download all the dependencies into a folder called 'neurons', and You will see the console output:

```
installing jquery@*
   GET http://r.ctx.io/jquery 200
   GET http://r.ctx.io/jquery/-/jquery-1.9.1.tgz 200
write /Users/ltebean/Desktop/colorify/neurons/jquery/1.9.1/jquery.js
```

## 3. Begin to Code

Now that `jquery` is installed, we can depend on it to reach our goal, edit index.js:

```js
var $ = require('jquery');

function colorify(selector, color){
  $(selector).css('background-color', color);
}

module.exports = colorify;
```

Our work is done! and you will find that we write code just the same way as in Node.js.






