# gulp-iconfont-css
> Generate (S)CSS file for icon font created with [Gulp](http://gulpjs.com/)

## Usage

First, install `gulp-iconfont-css` as a development dependency:

```shell
npm install --save-dev gulp-iconfont-css
```

Then, add it to your `gulpfile.js`:

```javascript
var iconfont = require('gulp-iconfont');
var iconfontCss = require('gulp-iconfont-css');

gulp.task('iconfont', function(){
  gulp.src(['app/assets/icons/*.svg'])
    .pipe(iconfontCss({
      path: 'app/assets/css/templates/_icons.scss',
      targetPath: '../../css/_icons.scss' // relative to gulp.dest below
    })
    .pipe(iconfont({
      fontName: 'Icons'
     }))
    .pipe(gulp.dest('app/assets/fonts/icons/'));
});
```

`gulp-iconfont-css` works well with `gulp-iconfont` but you can use it in a more modular fashion by directly using `gulp-svgicons2svgfont`, `gulp-svg2tff`, `gulp-ttf2eot` and/or `gulp-ttf2woff`.

## API

### iconfontCSS(options)

#### options.path
Type: `String`

The template path (optional, defaults to _icons.css provided with plugin).

#### options.targetPath
Type: `String`

The path where the (S)CSS file should be saved, relative to the path used in ```gulp.dest()``` (optional, defaults to ```_icons.css```).

#### options.engine
Type: `String`

The template engine to use (optional, defaults to ```lodash```). 
See https://github.com/visionmedia/consolidate.js/ for available engines. The engine has to be installed before using.

