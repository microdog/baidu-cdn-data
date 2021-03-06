# baidu-cdn-data [![Build Status](https://travis-ci.org/liangmingyi/baidu-cdn-data.png)](https://travis-ci.org/liangmingyi/baidu-cdn-data)

> [baidustatic](http://cdn.code.baidu.com/) CDN data for [google-cdn](https://github.com/passy/google-cdn).

This module makes it easy to replace references to your bower resources in your
app with links to the libraries on baidustatic.

## Getting started

Install: `npm install --save-dev google-cdn baidu-cdn-data`

### Example

*bower.json*:

```json
{
  "name": "my-awesome-app",
  "dependencies": {
    "jquery": "~2.0.0"
  }
}
```

```javascript
var googlecdn = require('google-cdn');

var bowerConfig = loadJSON('bower.json');
var markup = '<script src="bower_components/jquery/jquery.js"></script>';
googlecdn(markup, bowerConfig, {cdn: require('baidu-cdn-data')}, function (err, result) {
  if (err) {
    throw err;
  }

  assert.equal(result,
    '<script src="http://apps.bdimg.com/libs/jquery/2.0.3/jquery.min.js"></script>');
});
```

## License

MIT
