# gulp-tinypng-nokey-plus
Use the upload api of tinypng's homeage to compress images, so can use it without key.

模拟用户上传和下载的行为，来得到压缩图片，突破使用官网api每月500张限制

## Install
```
$ npm install --save-dev gulp-tinypng-nokey-plus
```

## Good logs
for example:
```
[14:15:01] gulp-tinypng-nokey : [tinypng request] 1.png

[14:15:04] gulp-tinypng-nokey : [compressing] Ok~ 1.png (26.8%)

[14:15:04] gulp-tinypng-nokey : [tinypng request] 2.jpg

[14:15:07] gulp-tinypng-nokey : [compressing] Ok~ 2.jpg (59.8%)

[14:15:07] gulp-tinypng-nokey : [tinypng request] test.js

[14:15:08] gulp-tinypng-nokey [error]:  test.js This file type is not supported

[14:13:40] gulp-tinypng-nokey : [compress completed] skiped: 0 imgs, compressed: 0 imgs, totalSize: 0%
```

## How to use
```
var gulp = require('gulp');
var tiny = require('gulp-tinypng-nokey-plus');

gulp.task('tinypng', function(cb) {
    gulp.src('src/*')
        .pipe(tiny())
        .pipe(gulp.dest('dist'));
});
```

## Intro
need upload files, so it may be unstable.Recommand to move this to the end of task.

尽量放到任务的最后一步，因为这个过程是要上传图片，再下载图片的，和网络稳定有关
