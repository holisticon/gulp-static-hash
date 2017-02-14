gulp-static-hash
=============

[![Build Status](https://travis-ci.org/holisticon/gulp-static-hash.svg?branch=master)](https://travis-ci.org/holisticon/gulp-static-hash)
[![Build status](https://ci.appveyor.com/api/projects/status/9f9v7r242agre6ji?svg=true)](https://ci.appveyor.com/project/holisticon-github/gulp-static-hash)

> A gulp plugin for cache files by adding a hash version append their name(like a.js?v=hash).

## Install

```
npm install --save-dev @holisticon/gulp-static-hash
```

Or if you want to use the development version (nightly build), which maybe not stable!:

```
npm install @holisticon/gulp-static-hash@next --save-dev
```

## Examples

### Default

```js
var gulp = require('gulp');
var staticHash = require('gulp-static-hash');

gulp.task('static-hash-html', function () {
	gulp.src('static/**/*.html')
		.pipe(staticHash({asset: 'static'}))
		.pipe(gulp.dest('dest'));
});
```

#### Input:

```html
<link rel="stylesheet" href="main.min.css">
<script src="main.min.js"></script>
<img src="main.png" />
```

#### Output:

```html
<link rel="stylesheet" href="main.min.css?v=8501b2b">
<script src="main.min.js?v=8501b2b"></script>
<img src="main.png?v=8501b2b" />
```

### Options

##### asset: 'static'

The path to assets in your project

##### exts: ['js', 'css', 'png']

The extension list need add hash version

##### md5BuildAsset: 'static'
The path to assets in your project used by create md5 file