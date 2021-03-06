# gulp-jshint-html-reporter

A simple reporter for gulp-jshint that writes it's output to a html file which looks pretty.

## Installation

```bash
$: npm install gulp-jshint-html-reporter --save
```

## Usage

```javascript
var gulp = require("gulp");
var jshint = require("gulp-jshint");

gulp.task("lint", function() {
  return gulp
    .src("./lib/*.js")
    .pipe(jshint())
    .pipe(
      jshint.reporter("gulp-jshint-html-reporter", {
        filename: __dirname + "/jshint-output.html",
        createMissingFolders: false
      })
    );
});
```

## Options

Plugin options:

Type: `filename`
Default: `"jshint-output.html"`

The filename to write output from jshint. When linting is successfull, the file is not created.

Type: `createMissingFolders`
Default: `false`

Enables or disables creation of any folders given in the filename that do not exist.
If disabled and the given path contains folders which do not exist, an ENOENT error is thrown.

## License

[MIT](http://opensource.org/licenses/MIT) © [the-phoenix](https://github.com/the-phoenix)

## Release History

- 0.1.0 Initial release
- 0.1.1 Minor fix with configuration
- 0.1.2 Minor bug fix on jshint output file
- 0.1.3 Add option for create missing folder
- 0.1.7 Update to nodejs 10.
