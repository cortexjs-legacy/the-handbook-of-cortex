# Gulp

Gulp is a great building system based on streams. This article is about how to make gulp work with cortex.

Suppose we split a very big JavaScript file into small pieces into the `src/` directory, and want to concat it into `index.js` before we pack the current package.

So, we have a `gulpfile.js`

```js
var gulp = require('gulp');
var concat = require('gulp-concat');

gulp.task('concat', function() {
  gulp.src('./src/*.js')
    .pipe(concat('index.js'))
    .pipe(gulp.dest('.'))
});
```

But we don't want to run `gulp concat` every time we execute `cortex build`, what should we do?

The `cortex.scripts.prebuild` will help.

## scripts.prebuild

`scripts.prebuild` is a custom command which will be spawned before cortex is going to pack your file.

We can specify this property in our `cortex.json` file:

```js
{
  "scripts": {
    "prebuild": "gulp"
  }
}
```

Then, each time we run `cortex build`, it will invoke the gulp task first.

When running `prebuild` script, cortex will add `./node_modules/.bin` to the environment `PATH`, so you need not to use `"./node_modules/.bin/gulp"`, just `"gulp"` is ok.

## More Prebuild Scripts

The value of `scripts.prebuild` could be an array of commands which will be execute one by one.

```js
{
  "scripts": {
    "prebuild": [
      "gulp",
      "jshint ./index.js"
    ]
  }
}
```

We can use `jshint` commandline, or `gulp-jshint` to do the job.

Actually, we can use any kind of scripts here, and different scripts together which is not recommended though :p

```js
{
  "scripts": {
    "prebuild": [
      "gulp",
      "grunt",
      "sh build.sh"
    ]
  }
}
```

## Attension

For using `gulp` or `grunt` as the cortex.scripts, it'd better to have `gulp` and the npm dependencies of current package. Or if other people clone your project to his local machine, or your project is going to be deployed by some CI system, there might be an "command not found" error.


