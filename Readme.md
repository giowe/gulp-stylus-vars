# gulp-stylus-vars

<div>
	<a href="https://www.npmjs.com/package/slush-aws-lambda"><img src='http://img.shields.io/npm/v/gulp-stylus-vars.svg?style=flat'></a>
	<a href="https://www.npmjs.com/package/slush-aws-lambda"><img src='https://img.shields.io/npm/dm/gulp-stylus-vars.svg?style=flat-square'></a>
	<a href="https://david-dm.org/giowe/gulp-stylus-vars"><img src='https://david-dm.org/giowe/gulp-stylus-vars.svg'></a>
	<a href="https://www.youtube.com/watch?v=Sagg08DrO5U"><img src='http://img.shields.io/badge/gandalf-approved-61C6FF.svg'></a>
</div>

Inject variables in stylus files from a js object.

## Usage

```
npm install gulp-stylus-vars
```

```js

var stylusVars = require('gulp-stylus-vars');

gulp.task('stylus', function() {
  var variables = {
    stringTest: "hello",
    string2Test: "https://github.com/giowe/gulp-stylus-vars",
    integerTest: 123,
  };

  return gulp.src([
    'src/styles/main.styl'
  ])
    .pipe(stylusVars(variables, { verbose: true }))
    .pipe(stylus())
    .pipe(gulp.dest('dist'))
});
```

This script will prepend the following code to your main.styl file:

```
stringTest = hello
string2Test = "https://github.com/giowe/gulp-stylus-vars"
integerTest = 123
```

So you can use all those variables inside your stylus file.
Quotes will be added when needed via regex.
