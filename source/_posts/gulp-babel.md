---
title: gulp-babel转化es2016
date: 2016-05-18 00:32:54
tags: gulp插件
------------

各大浏览器厂商对es2015功能支持不完全,等到全部支持会等很长时间,如果现在使用es2015,可以选择babel一个将ES6/ES7写的代码转换为ES5代码的编译器.

我们选择使用gulp自动化编译生成es5代码.

假设你已经安装过了nodejs.

配置开发环境:

1. 建立工程目录:  
``` bash
$mkdir test && cd test
```

2. 新建工程配置文件package.json 
``` bash
$npm init
```
3. 安装gulp工具
``` bash
$npm install --save-dev gulp gulp-babel gulp-concat gulp-sourcemaps babel-preset-es2015
```

4. 新建gulp配置文件
``` bash
$vim gulpfile.js
```

写入代码gulpfile.js:
``` javascript
  const gulp = require("gulp");  
  const sourcemaps = require("gulp-sourcemaps");  
  const babel = require("gulp-babel");  
  const concat = require("gulp-concat");    
  
  gulp.task('default', () =>  
      gulp.src('src/**/*.js')  
          .pipe(babel({  
              presets: 'es2015'  
          }))  
          .pipe(gulp.dest('dist'))  
  );    
  
  //生成sourcemaps   
  gulp.task('all', () =>  
      gulp.src('src/**/*.js')  
          .pipe(sourcemaps.init())  
          .pipe(babel({  
              presets: 'es2015'  
          }))  
          .pipe(concat('all.js'))  
          .pipe(sourcemaps.write('.'))  
          .pipe(gulp.dest('dist'))  
  );
```

5. 测试是否配置成功
``` bash
mkdir src && cd src && vim app.js
```

写入代码:

``` javascript
  function f() {   
      let x;  
      {  
        // okay, block scoped name  
        const x = "sneaky";  
        // error, const  
        //x = "foo";  
        console.log(x);  
      }  
      // okay, declared with `let`  
      x = "bar";  
      // error, already declared in block  
      //let x = "inner";  
      console.log(x);  
  }   
  f();
```


6.执行

``` bash
$gulp
```

会自动生成dest目录,包含app.js文件,是转化过的js.恭喜你已经学会!