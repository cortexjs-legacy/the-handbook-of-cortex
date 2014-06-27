# Always remember to test

Now lets's add our testcase.

## 1. Install Cortex Test

Currently `cortex-test` is in a seperate package, so install it by:

```
npm install -g cortex-test
```


## 2. Add a test page

Add a page called colorify.html in the test folder

```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>
	<div id="paper"></div>
</body>
</html>
```

## 3. Write test cases

`cortex-test` use `mocha` as the test framework, edit test/colorify.js,

```js
'use strict';

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

## Run the test case

In the project root path, run:

```
cortex test
```

A page will be open and you can see the test result there.

