Restberry-Logger
================

[![](https://img.shields.io/npm/v/restberry-logger.svg)](https://www.npmjs.com/package/restberry-logger) [![](https://img.shields.io/npm/dm/restberry-logger.svg)](https://www.npmjs.com/package/restberry-logger)

Logger class for HTTP requests and responses. Color coded for UNIX console.

## Install

```
npm install restberry-logger
```

## Usage

Log requests and responses from common NodeJS Web Application
Frameworks like ExpressJS or RestifyJS (only tested with ExpressJS).

```
var logger = require('restberry-logger');

var req = ... // request object from for example express
logger.request(req);
// 2014-05-09T19:58:41.726Z|172.16.122.129|POST|/api/v1/foo|<{
//     "name": "bar"
// }>

var res = ... // response object from for example express
var json = ... // the json object to return
logger.response(req, json);
// 2014-05-09T19:58:41.732Z|172.16.122.129|201|<{
//   "foo": {
//     "href": "/api/v1/teams/536d3371f927a55164ba1911",
//     "id": "536d3371f927a55164ba1911",
//     "name": "bar",
//   }
// }>
```

May also use it to log info.

```
logger.info('RESTBERRY', 'this is my message');
// 2014-05-09T19:58:41.732Z|RESTBERRY|this is my message
```
