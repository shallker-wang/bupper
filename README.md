bupper
==========

A Nodejs Buffer helper.

## Installation
Use npm
```shell
npm install git://github.com/shallker-wang/bupper.git
```

or add to your package dependencies
```json
{
  "dependencies": {
    "bupper": "git://github.com/shallker-wang/bupper.git"
  }
}
```

## Quick Start
Concat Buffer chunks with `.add(chunk)` and output them together using `.combine()`
```javascript
var Bupper = require('bupper');
var http = require('http');
http.createServer(function(req, res) {
  req.on('data', function(chunk) {
    Bupper.add(chunk);
  });
  req.on('end', function() {
    console.log( Bupper.combine().toString() )
  })
}).listen(80);
```

## Todo
* write a test
