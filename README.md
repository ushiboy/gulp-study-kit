#gulp

社内勉強会用gulpの使い方

##インストール

gulpコマンドを使えるようにする。

```
$ npm install -g gulp
```

##プロジェクトでの利用

設定で使うのでこちらでも入れる。

```
$ mkdir project_dir
$ cd project_dir
$ npm init
$ npm install --save-dev gulp
```

##タスクの設定

gulpfile.jsで行う。
```javascript
var gulp = require('gulp');

gulp.task('hoge', function() {
  // $ gulp hoge
});

gulp.task('default', ['hoge'], function() {
  // $ gulp
});
```

##依存プラグインの簡略化

gulp-load-pluginsを使う。

```javascript
var gulp
// var imagemin = require('gulp-imagemin');
var $ = require('gulp-load-plugins')();

gulp.task('img', function() {
  gulp.src('./src/img/*.jpg')
  // .pipe(imagemin())
  .pipe($.imagemin())
  .pipe(gulp.dest('./dist/img'));
});
```
