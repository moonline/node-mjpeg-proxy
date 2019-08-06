node-mjpeg-proxy
================

A node.js module to proxy MJPEG requests. Supports multiple client consuming a single stream. Fixes an iOS 6 issue with some MJPEG steams.

Installation
------------

From npm:

``` bash
$ npm install mjpeg-proxy
```

From source:

``` bash
$ git clone https://github.com/legege/node-mjpeg-proxy.git
$ cd node-mjpeg-proxy
$ npm install
```

Example
-------

### Example Usage

``` js
var MjpegProxy = require('mjpeg-proxy').MjpegProxy;
var express = require('express');
var app = express();

app.get('/index1.jpg', new MjpegProxy('http://admin:admin@192.168.1.109/cgi/mjpg/mjpg.cgi').proxyRequest);
app.listen(8080);
```

Here, it will create a proxy to the source video feed (`http://admin:admin@192.168.1.109/cgi/mjpg/mjpg.cgi`). You can now access the feed at `http://localhost:8080/index1.jpg`.

API
---

### MjpegProxy

``` js
var mjpegProxy = new MjpegProxy(mjpegUrl);
``` 

Returns: a `MjpegProxy` instance for the MJPEG stream at `mjpegUrl` URL.

Credits
-------

Original prototype version from:

  * Phil Rene ([philrene](http://github.com/philrene))
  * Chris Chua ([chrisirhc](http://github.com/chrisirhc))
