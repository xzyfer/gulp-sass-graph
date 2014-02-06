
> Read the import graph from passed sass files to work with dependencies

Only pass along Sass files that have changed, along with dependencies. 


## Install

Install with [npm](https://npmjs.org/package/gulp-sass-graph)

```
npm install --save-dev gulp-sass-graph
```


## Example

```js
gulp.task('watch-sass', function(cb) {
  return watch({glob:'resources/assets/css/**/*.scss', emitOnGlob: false, name: "Sass"})
    .pipe(sassGraph(sassLoadPaths))
    .pipe(sass({loadPath: sassLoadPaths}))
    .pipe(notify('Sass compiled <%= file.relative %>'))
    .pipe(gulp.dest('web/dist/css'))
    .pipe(livereload());
});
```

## License

MIT © [Lachlan Donald](http://lachlan.me)
