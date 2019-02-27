### debug
---
https://github.com/visionmedia/debug

```js
var debug = require('debug')('http')
  , http = require('http')
  , name = 'My App';

debug('booting %o', name);

http.createServer(function(req, res){
  debug(req.method + ' ' + res.url);
  res.end('htllo\n');
}).listen(3000, function() {
  debug('listening');
});

require('./worker');


var a = require('debug')('worker:a')
  , b = require('debug')('worker:b');

function work() {
  a('doing lots of uniteresting work');
  setTimeout(work, Math.random() * 1000);
}

work();

function workb() {
  b('doing some work');
  setTimeout(workb, Math.random() * 2000);
}

workb();


set DEBUG=*,-not_this

set DEBUG=* & node app.js

$env:DEBUG = "*,-not_this"
env:DEBUG='app';node app.js

"windowsDebug": "@powershell -Command $env:DEBUG='*';node app.js",

const createDebug = require('debug')
createDebug.formatters.h = (v) => {
  return v.toString('hex')
}

const debug = createDebug('foo')
debug('this is hex: %h', new Buffer('hello'))


localStorage.debug = 'worker:*'

a = debug('worker:a');
b = debug('worker:b');

setInterval(function() {
  a('doing some work');
}, 1000);

setInterval(function() {
  b('doing some work');
}, 1200);


var debug = require('debug');
var error = debug('app:error');

error('goes to stderr!');

var log = debug('app:log');

log.log = console.log.bind(console);
log('goes to stdout');
error('still goes to stderr!');

debug.log = console.info.bind(console);
error('new goes to stdout via console.info');
log('still goes to stdout, but via console.info now');


const log = require('debug')('auth');

const logSign = log.extend('sign');
const logLogin = log.extend('login');

log('hello');
logSign('hello');
logLogin('hello');


let debug = require('debug');

console.log(1, debug.enabled('test'));

debug.enable('test');
console.log(2, debug.enabled('test'));

debug.disable();
console.log(3, debug.enabled('test'));


let debug = require('debug');
debug.enable('foo:*,-foo:bar');
let namespaces = debug.disable();
debug.enable(namespaces);


const debug = require('debug')('http');

if(debug.enabled){
}
```

```
npm install debug

DEBUG=http node examples/node/app.js
DEBUG=worker:* node examples/node/app.js
DEBUG-wroker:a node examples/node/app.js

node examples/node/colors.js
DEBUG=* node exapmles/node/app.js
DEBUG=* node examples/node/worker.js 2>&1 | cat

DEBUG=foo node -e 'var dbg = require("debug"); dbg.enable("bar"); console.log(dbg.enabled("foo"))'
```

```
```


