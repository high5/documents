# flux-getting-started

[Introduction to Facebook's Flux architecture](http://ryanclark.me/getting-started-with-flux/)

## structure 1

```
flux-getting-started
├ gulp
│ ├ prod
│ │ ├ copy.js
│ │ ├ html.js
│ │ ├ scripts.js
│ │ └ styles.js
│ ├ copy-html.js
│ ├ copy-libs.js
│ ├ scripts.js   [for javascript with gulp, browserify]
│ ├ server.js  
│ ├ styles.js    [for css with gulp-ruby-sass]
│ └ watch.js
├ public
│ └ src
│    ├ fonts
│    │ ├ fontawesome-webfont.eot
│    │ ├ fontawesome-webfont.svg
│    │ ├ fontawesome-webfont.ttf
│    │ └ fontawesome-webfont.woff
│    ├ img
│    │ └ favicon.ico
│    ├ js
│    │ ├ actions
│    │ │ └ .gitignore
│    │ ├ components
│    │ │ └ replyBox.jsx
│    │ ├ dispatchers
│    │ │ └ .gitignore
│    │ ├ partials
│    │ │ ├ header.jsx
│    │ │ ├ messageBox.jsx
│    │ │ └ userList.jsx
│    │ ├ stores
│    │ │ └ user.js
│    │ ├ app.jsx
│    │ └ utils.js
│    ├ scss
│    │ ├ components
│    │ │ └ _replyBox.scss
│    │ ├ fonts
│    │ │ └ _fontawesome.scss
│    │ ├ partials
│    │ │ ├ _header.scss
│    │ │ ├ _messageBox.scss
│    │ │ └ _userList.scss
│    │ ├ _defaults.scss
│    │ ├ _misc.scss
│    │ ├ _normalize.scss
│    │ ├ _print.scss
│    │ └ app.scss
│    └ index.html

```

## package.json

```
{
  "name": "all-about-flux",
  "version": "0.0.0",
  "description": "Getting started with Flux",
  "main": "./",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/rynclark/flux-getting-started.git"
  },
  "keywords": [
    "flux"
  ],
  "author": "Ryan Clark",
  "license": "MIT",
  "bugs": {
    "url": "https://github.com/rynclark/flux-getting-started/issues"
  },
  "homepage": "https://github.com/rynclark/flux-getting-started",
  "devDependencies": {
    "browserify": "^5.10.1",
    "connect-livereload": "~0.3.2",
    "express": "~3.4.8",
    "gulp": "^3.8.11",
    "gulp-autoprefixer": "0.0.7",
    "gulp-livereload": "^0.3.2",
    "gulp-notify": "^1.2.5",
    "gulp-plumber": "~0.5.6",
    "gulp-preprocess": "^1.1.1",
    "gulp-rename": "^1.2.0",
    "gulp-ruby-sass": "^0.7.1",
    "multipipe": "^0.1.1",
    "reactify": "^0.17.1",
    "tiny-lr": "0.0.5",
    "vinyl-transform": "0.0.1"
  },
  "dependencies": {
    "flux": "^2.0.1",
    "object-assign": "^2.0.0"
  }
}
```




## bower.json

```
{
  "name": "flux-getting-started",
  "version": "0.0.0",
  "homepage": "https://github.com/rynclark/flux-getting-started",
  "authors": [
    "Ryan Clark"
  ],
  "description": "Getting started with Flux",
  "keywords": [
    "flux",
    "getting",
    "started"
  ],
  "license": "MIT",
  "private": true,
  "ignore": [
    "**/.*",
    "node_modules",
    "public/libs",
    "test",
    "tests"
  ],
  "dependencies": {
    "react": "~0.12.2"
  }
}

```

## gulpfile.js detail

```
var gulp = require('gulp');

/**
 * Development
 */
var server = require('./gulp/server');
var scripts = require('./gulp/scripts');
var styles = require('./gulp/styles');
var watch = require('./gulp/watch');
var copyLibs = require('./gulp/copy-libs');
var copyHTML = require('./gulp/copy-html');

gulp.task('server', server);
gulp.task('scripts', scripts);
gulp.task('styles',  styles);
gulp.task('watch', watch);
gulp.task('copy:html', copyHTML);
gulp.task('copy:libs', copyLibs);

gulp.task('build', [
  'scripts',
  'styles'
  ]);

gulp.task('test', [
  'build',
  'mock',
  'karma'
  ]);

gulp.task('default', [
  'server',
  'build',
  'copy:libs',
  'copy:html',
  'watch'
  ]);

```
