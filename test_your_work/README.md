# Always Remember to Test

Now let's add some testcases.

## 1. Install `cortex-test`

Currently `cortex-test` is in a seperate package, so install it by:

```
npm install -g cortex-test
```


## 2. Add a Test Page

Create a page called colorify.html in the test folder, and just add the necessary markup:

```html
<div id="paper"></div>
```

## 3. Write test cases

`cortex-test` use `mocha` as the test framework, edit test/colorify.js,

```js
var colorify = require('../index');
var $ = require('jquery');

var assert = require('assert');

describe('colorify', function() {
  it('should set the background color properly', function() {
    colorify('#paper', 'red');
    assert($('#paper').css('background-color'), 'red');
  });
});
```

## Run the test

In the project root path, run:

```bash
cortex test
```

A page will be open in your browser and you can see the test result there.

