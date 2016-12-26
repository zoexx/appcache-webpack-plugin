# Application Cache plugin for Webpack

## * 此版本修改了原版中 publicPath 拼接部分，支持[hash]的引用，并不会同步更新版本，请使用[原版](https://www.npmjs.com/package/appcache-webpack-plugin)

## Usage

```javascript

var AppCachePlugin = require('appcache-webpack-plugin');

module.exports = {
  plugins: [
    new AppCachePlugin({
      cache: ['someOtherAsset.jpg'],
      network: null,  // No network access allowed!
      fallback: ['failwhale.jpg'],
      settings: ['prefer-online'],
      exclude: ['file.txt', /.*\.js$/],  // Exclude file.txt and all .js files
      output: 'my-manifest.appcache'
    })
  ]
}
```

Arguments:

* `cache`: An array of additional assets to cache.
* `network`: An array of assets that may be accessed via the network.
  Defaults to `['*']`.
* `fallback`: An array of fallback assets.
* `settings`: An array of settings.
* `exclude`: An array of strings or regex patterns. Assets in the compilation
that match any of these patterns will be excluded from the manifest.
* `output`: The filename to write the appcache to

## License

[MIT](http://www.opensource.org/licenses/mit-license.php)
