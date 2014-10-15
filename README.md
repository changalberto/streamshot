streamshot
==========

Take Screenshot from headless browsers PhantomJS, SlimerJS, TrifleJS as a stream. Based off the source code of [screenshot-stream](https://github.com/kevva/screenshot-stream)

##Usage
```javascript
var streamshot = require('../lib/streamshot.js');
var stream = streamshot([engine], [url], [size]);
```

###Example
```javascript
'use strict';

var concat = require('concat-stream'),
    isPNG = require('is-png'),
    streamshot = require('../lib/streamshot.js');

var stream = streamshot('slimerjs', 'http://google.com', '1024x800');

stream.pipe(concat(function(data){
    console.log(data);
    console.log(isPNG(data));
}));

```
