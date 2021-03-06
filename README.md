# webpack-concat-plugin
[![npm package](https://img.shields.io/npm/v/webpack-concat-plugin.svg)](https://www.npmjs.org/package/webpack-concat-plugin)
[![npm downloads](http://img.shields.io/npm/dm/webpack-concat-plugin.svg)](https://www.npmjs.org/package/webpack-concat-plugin)
> a plugin to help webpack to concat js and inject to html-webpack-plugin
### Why
webpack is really powerful, but when I just want to concat the static file and inject to html without webpack JSONP code wrapper. After all days search, it seems impossible to do that without other tool's help.

### Install
```
npm install webpack-concat-plugin --save-dev
```

### Features
* concat
* inject to html(with html-webpack-plugin)

### Usage
```
const ConcatPlugin = require('webpack-concat-plugin');

new ConcatPlugin({
    uglify: true, // or you can set uglifyjs options
    useHash: true, // md5 file
    sourceMap: true, // generate sourceMap
    name: 'flexible', // used in html-webpack-plugin
    fileName: '[name].[hash].bundle.js', // would output to 'flexible.d41d8cd98f00b204e980.bundle.js'
    filesToConcat: ['./src/lib/flexible.js', './src/lib/makegrid.js', 'jquery'],
    manifestName: 'manifest.json' // if want to use this option, please use webpack-manifest-plugin@2.0.0-rc.1 or above first
});

```
### Inject to html(by hand)
```
doctype html
...
    script(src=htmlWebpackPlugin.files.webpackConcat.flexible)
...
```

### TODO
* add css support
* auto inject to html
