---
title: next开启服务报错
date: 2020-06-25 13:01:22
categories:- 笔记
tags:- 学习
- 代码
---
今天给NEXT主题新添加分享和CND加速功能，修改主题配置文件之后开启本地预览服务后报错：
```bash
Unhandled rejection Error: ENOENT: no such file or directory, open 'C:\github\blog\themes\next\layout\_scripts\schemes\.swig'
    at Error (native)
    at Object.fs.openSync (fs.js:584:18)
    at Object.fs.readFileSync (fs.js:431:33)
    at Object.ret.load (C:\github\blog\node_modules\swig\lib\loaders\filesystem.js:55:15)
    at compileFile (C:\github\blog\node_modules\swig\lib\swig.js:695:31)
    at Object.eval [as tpl] (eval at <anonymous> (C:\github\blog\node_modules\swig\lib\swig.js:498:13), <anonymous>:293:18)
    at compiled [as _compiledSync] (C:\github\blog\node_modules\swig\lib\swig.js:619:18)
    at tryCatcher (C:\github\blog\node_modules\bluebird\js\release\util.js:16:23)
    at null._compiled (C:\github\blog\node_modules\bluebird\js\release\method.js:15:34)
    at View.render (C:\github\blog\node_modules\hexo\lib\theme\view.js:29:15)
    at C:\github\blog\node_modules\hexo\lib\hexo\index.js:387:25
    at tryCatcher (C:\github\blog\node_modules\bluebird\js\release\util.js:16:23)
    at C:\github\blog\node_modules\bluebird\js\release\method.js:15:34
    at RouteStream._read (C:\github\blog\node_modules\hexo\lib\hexo\router.js:134:3)
    at RouteStream.Readable.read (_stream_readable.js:336:10)
    at resume_ (_stream_readable.js:726:12)
    at _combinedTickCallback (node.js:383:13)
    at process._tickCallback (node.js:407:11)
```
谷歌大法之后几乎所有的解决方法都是主题config文件语法错误，遂使用YAML在线解析工具进行语法查错：
```
https://www.bejson.com/validators/yaml_editor/
```
根据提示一一将空格加好后问题解决。