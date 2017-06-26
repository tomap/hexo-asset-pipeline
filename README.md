# hexo-asset-pipeline

Asset pipeline for [Hexo](https://hexo.io/) to support minification and optimization of HTML, CSS, JS and images.

Supports hexo 3.x.x.

## Installation
``` bash
$ npm install hexo-asset-pipeline --save
```

## Configuration


Add the following snippet in `_config.yml`. 

Minimal config to enable filters for HTML, CSS, Js and images.
```yaml
asset_pipeline:
  revisioning: true
  clean_css:
    enable: true
  uglify_js:
    enable: true
  imagemin:
    enable: true
  html_minifier:
    enable: true
```
- **revisioning** - Enabling revisioning(md5 hash) of assets. Defaults to false.
- **clean_css** - Adding options for [clean-css](https://www.npmjs.com/package/clean-css).
- **uglify_js** - Adding options for [uglify-js](https://www.npmjs.com/package/uglify-js).
- **imagemin** - Adding options for [imagemin](https://www.npmjs.com/package/imagemin).
- **html_minifier** - Adding options for [html-minifier](https://www.npmjs.com/package/html-minifier).


## Components
Following are the modules that are being used to process differnet types of assets.

### HTML (html_minifier)

[html-minifier](https://www.npmjs.com/package/html-minifier) is used to minify the HTML files.

#### Options
``` yaml
html_minifier:
  enable: true
  ignore_error: false
  exclude:
```
- **enable** - Enable the plugin. Defaults to `false`.
- **ignore_error** - Ignore the error occurred on parsing html
- **exclude**: Exclude files

**Note**: Check [html-minifier](https://www.npmjs.com/package/html-minifier#options-quick-reference) for more options.

### Javascripts (uglify_js)
[uglify-js](https://www.npmjs.com/package/uglify-js) is used to minify javascripts.

#### Options
``` yaml
uglify_js:
  enable: true
  mangle: true
  output:
  compress:
  exclude: 
    - '*.min.js'
```
- **enable** - Enable the plugin. Defaults to `false`.
- **mangle**: Mangle file names
- **output**: Output options
- **compress**: Compress options
- **exclude**: Exclude files


**Note**: Check [uglify-js](https://www.npmjs.com/package/uglify-js#minify-options) for more options.

### Stylesheets (clean_css)
[clean-css](https://www.npmjs.com/package/clean-css) is used to minify stylesheets.

#### Options
``` yaml
clean_css:
  enable: true
  exclude: 
    - '*.min.css'
```
- **enable** - Enable the plugin. Defaults to `false`.
- **exclude**: Exclude files


**Note**: Check [clean-css](https://www.npmjs.com/package/clean-css#use) for more options.


### Images (imagemin)
[imagemin](https://www.npmjs.com/package/clean-css) is used to optimize images.

#### Options
```yaml
imagemin:
  enable: true
  interlaced: false
  multipass: false
  optimizationLevel: 2
  pngquant: false
  progressive: false
```
- **enable** - Enable the plugin. Defaults to `false`.
- **interlaced** - Interlace gif for progressive rendering. Defaults to `false`.
- **multipass** - Optimize svg multiple times until it’s fully optimized. Defaults to `false`.
- **optimizationLevel** - Select an optimization level between 0 and 7. Defaults to `2`.
- **pngquant** - Enable [imagemin-pngquant](https://github.com/imagemin/imagemin-pngquant) plugin. Defaults to `false`.
- **progressive** - Lossless conversion to progressive. Defaults to `false`.
- **exclude** - Exclude specific types of image files, the input value could be `gif`,`jpg`, `png`, or `svg`. Default to null.

**Note**: Check [imagemin](https://www.npmjs.com/package/clean-css#use) for more options.

