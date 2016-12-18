<!-- page_number: true -->
<!-- $size: 16:9 -->

![](https://cloud.githubusercontent.com/assets/124117/21172360/cdb0d6be-c214-11e6-87ab-a7ee3363fa8a.png)

# Node.js: Getting started with Beginner

---

# Understanding Node.js

- Node.js or [node](https://github.com/nodejs/node)
- Javascript runtime built on [Chrome's V8 Javascript engine](https://developers.google.com/v8/)
- Working as Lighten and Faster on Multi Platforms
- Asynchronous I/O with [libuv](https://github.com/libuv/libuv)
- Non-blocking and Event-driven with Event loop
- One of [the biggest](http://www.modulecounts.com/) [Open Source Echosystem](https://nodejs.org/en/foundation/) in the world

---

## High-performance for Low Resource Consumer

- Low resource consumer, Allowing to use in Embedded system
- Managing about over 3000 request-per-second on single core/thread
- Powerfull debugging tools for optimizing performance
---

![](https://github.com/codebusking/resource/raw/master/images/v8/v8-logo.png)

## V8

- High-performance Javascript engine for Chromium / Chrome
- Used for multiple application. Chromium, Node.js, Electron and Embedded
- [Implements ES201](http://kangax.github.io/compat-table/es2016plus/)5(ECMAScript) [stage-x](https://github.com/tc39/proposals)
- Node.js will be supported to be using multiple engine (ex. Microsoft Edge's  [ChakraCore](https://github.com/nodejs/node/pull/4765))

---

![50%](https://raw.githubusercontent.com/libuv/libuv/master/img/banner.png)

## Asynchronous I/O via libuv

- Multi-platform supporting library
- Full-featured event loop backed by epoll, kqueue, IOCP, event ports
- Asynchrounous I/O for TCP/UDP/DNS/File system

---

## Non-blocking and Event-driven with Event loop

- Non-blocking is a primitive way of managing I/O
- Event-driven langunage(eg, JavaScript) is perfectly match up for Non-blocking
- Event loop backed up JavaScript form I/Os and other events

---

### I/O Models in Unix Network Programming Book

---

#### Non-blocking I/O with BSD socket APIs

![center 120%  main-qimg-6043fb09e7ce42274c5975464e904dd6](https://cloud.githubusercontent.com/assets/124117/21171811/9c6d0418-c211-11e6-8816-5f3a33a716ef.png)

---

#### Blocking I/O with BSD socket APIs

![center 120% main-qimg-5ac7b97f556b92dc84efe1b97f71da97](https://cloud.githubusercontent.com/assets/124117/21171812/9c8e46d2-c211-11e6-96d8-7b93c9598f26.png)

---

#### Asyncronous I/O

![center 120% main-qimg-12f933673e133866898a4a43a16c320e](https://cloud.githubusercontent.com/assets/124117/21171810/9c475268-c211-11e6-817b-d349a27f0e75.png)

---

### Blocking call with C

```c
#include "stdio.h"
#include <unistd.h>

void fp() {
  printf("3\n");
}

void fp_call(void (*fp)(void)) {
  fp();
}

int main() {
  printf("1\n");  
  printf("2\n");
  usleep(1000 * 2000);
  fp_call(&fp);
  return 0;
}
```

---

### Non-blocking call with Node.js

```
function fp() {
  console.log('2');
}
console.log('1');

setTimeout(fp, 2000);

console.log('3');
```

---

### Comapring calling of I/O with Node.js

```
const fs = require('fs');

fs.stat(',', (err, stats) => console.log(err, stats)); // asyncronous
const stat = fs.lstatSync('.'); // synchronous
```

---

![bg original](https://cloud.githubusercontent.com/assets/124117/21172038/03beb692-c213-11e6-8d75-0a1bdd8d963c.png)

---

![bg original 75%](https://cloud.githubusercontent.com/assets/124117/21172036/03b7b5e0-c213-11e6-9e29-643b4b8b4b7d.png)

---

![bg original 75%](https://cloud.githubusercontent.com/assets/124117/21172039/03bf1b6e-c213-11e6-8c59-3cc36dc59db2.png)

---

![bg original 75%](https://cloud.githubusercontent.com/assets/124117/21172037/03bd384e-c213-11e6-83b7-d636f62f75ac.png)

---

![bg original 75%](https://cloud.githubusercontent.com/assets/124117/21172040/03db4546-c213-11e6-9dec-41aff95426a6.png)

---

![bg original 75%](https://cloud.githubusercontent.com/assets/124117/21172042/03e5316e-c213-11e6-9230-3fb204ec79e4.png)

---

![bg original 75%](https://cloud.githubusercontent.com/assets/124117/21172041/03e3ca68-c213-11e6-984d-427191a89d65.png)

---

![bg original 75%](https://cloud.githubusercontent.com/assets/124117/21172043/03e54c26-c213-11e6-8bb3-8cb634499c6d.png)

---

![bg original 75%](https://cloud.githubusercontent.com/assets/124117/21172044/03f8ba86-c213-11e6-9457-089f0133ec7f.png)

---


```js
// QUIZ, getting result in order

// call with SetImmediate
setImmediate(() => console.log("1"));

// call with setTimeout
setTimeout(() => console.log("2"), 0);

// call with Promise in sync
Promise.resolve().then(() => console.log('3'));

// IIFE, immediately-invoked function expression
(() => console.log('4'))();

// last call for app
process.on('beforeExit', () => {
    console.log('0');
});
```

---

![bg original](https://i.ytimg.com/vi/OV2484MKwhw/maxresdefault.jpg)

---

[![center](https://upload.wikimedia.org/wikipedia/commons/d/db/Npm-logo.svg)](https://www.npmjs.com/)

---

![original center](https://cloud.githubusercontent.com/assets/124117/21172366/d31316a8-c214-11e6-8c7e-aa4ed83c6e5d.png)

---

![bg original 70%](https://s3.amazonaws.com/media-p.slid.es/uploads/136956/images/2592846/Screenshot_2016-04-20_17.56.47.png)

---

# Getting Started Node.js

- [Node 6.x.x](https://nodejs.org/dist/latest-v6.x/docs/api/) - [LTS veriosn on DEC, 2016](https://github.com/nodejs/LTS#lts_schedule)
- [NVM](https://github.com/creationix/nvm) or [n](https://github.com/tj/n) for managing versions of node
- Javascript
- Fundamentals to Node.js
- [NPM](https://docs.npmjs.com/)(May with also [yarn](https://github.com/yarnpkg/yarn)) for Node.js projects

---

![bg original 120%](https://cloud.githubusercontent.com/assets/4721750/21022378/93807b6c-bd63-11e6-9557-c37a51ca913c.png)

---

## Installing and Managing node with NvM

> using by [NVM](https://github.com/creationix/nvm) or [n](https://github.com/tj/n)

```
# download and install NVM
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash

# get versions can be installable
nvm ls-remote

# install node
nvm install v6.9.1
nvm install --lts

# get versions installed
nvm ls

# use a version
nvm use v6.9.1
```

---

![bg original center 100%](https://cloud.githubusercontent.com/assets/124117/21205653/c1e5ab8e-c2a0-11e6-994e-a1ae22e44f23.png)

---
[![center 150%](https://cloud.githubusercontent.com/assets/124117/21137039/859b6122-c16b-11e6-89f8-956c3f0a3cac.png)](https://github.com/codebusking/javascript-summary-of-javascript-guide-on-mdn)

![center 80%](https://cloud.githubusercontent.com/assets/124117/21137011/6d563de4-c16b-11e6-9adc-6694e433ce34.png)

---

## Fundamentals to Node.js

> globals, JavaScript for Node.js, Core module and more

---

### globals (global objects)

- Available in all Node.js modules, but not global scope
- Number of built-in objects in global objects, which are globally accessible
- The top-level scope is not the global scope, its local of Node.js modle
	- `var foo` won't not be in global scope

---

- **console**: Used to print to stdout and stderr `console.log("hello")`
- **__dirname**: The dirname of currently executing script in
- **__filename**: The filename of the code being executed
- **global**: Number of built-in objects in global objects
- **module**: Reference to the current module
- **exports**: Export object of current module, reference to the module.export
- **require(id)**: Load and get a reference to another module, will return `the module.exports` of the anothe module 
- **process**: Information about current node.js process
- **setImmediate** / **setInterval** / **setTimeout** for timer

---

#### console

> provides a simple debugging console that is similar to the JavaScript console mechanism provided by web browsers

```js
// Prints: hello world, to stdout
console.log('hello world');

// Prints: hello world, to stdout
console.log('hello %s', 'world');

// Prints: [Error: Whoops, something bad happened], to stderr
console.error(new Error('Whoops, something bad happened')); 

const name = 'Will Robinson';
console.warn(`Danger ${name}! Danger!`);
```
---

#### __dirname / __filename

> `__dirname`, The name of the directory that the currently executing script resides in. `__filename`, This is the resolved absolute path of this code fil

```js
// User/username/Projects/app/app.js
console.log(__filename); // User/username/Projects/app/app.js
console.log(__dirname); // User/username/Projects/app
```

---

#### module

> Reference to the current module, be in each module `not global`

```js
> module
Module {
  id: '<repl>',
  exports: {},
  parent: undefined,
  filename: null,
  loaded: false,
  children: [],
  paths:
   [ '/Users/node_modules',
     '/node_modules',
     '/Users/ragingwind/.node_modules',
     '/Users/ragingwind/.node_libraries',
     '/Users/ragingwind/.nvm/versions/node/v6.9.1/lib/node' ] }
```

---

#### export and require(id)

> Node.js has a simple module loading system. In Node.js, files and modules are in one-to-one correspondence

```js
// foo.js
const circle = require('./circle.js');
console.log(`The area of a circle of radius 4 is ${circle.area(4)}`);

// circle.js
const PI = Math.PI;
exports.area = (r) => PI * r * r;
exports.circumference = (r) => 2 * PI * r;
```

---

> if you want to export a complete object in one assignment instead of building it one property at a time, assign it to module.exports instead of exports

```js
// bar.js
const square = require('./square.js');
var mySquare = square(2);
console.log(`The area of my square is ${mySquare.area()}`);

// square.js
// assigning to exports will not modify module, must use module.exports
module.exports = (width) => {
  return {
    area: () => width * width
  };
}
```

---

##### module wrapper

> Before a module's code is executed, Node.js will wrap it with a function wrapper that looks like the following

```js
(function (exports, require, module, __filename, __dirname) {
  // Your module code actually lives in here
});
```

- Node.js keeps top-level variables (defined with var, const or let) scoped to the module rather than the global object.
- Node.js helps to provide some global-looking variables that are actually specific to the module, exports, require, module, __filename, __dirname

---

##### exports alias

> The exports variable that is available within a module starts as a reference to module.exports. As with any variable, if you assign a new value to it, it is no longer bound to the previous value. ignore exports and only use module.exports.

```js
function require(...) {
  // ...
  ((module, exports) => {
    // Your module code here
    exports = some_func;        // re-assigns exports, exports is no longer
                                // a shortcut, and nothing is exported.
    module.exports = some_func; // makes your module export 0
  })(module, module.exports);
  return module;
}
```

---

##### module cycle

```js
// a.js
console.log('a starting'); // 2
exports.done = false;
const b = require('./b.js');
console.log('in a, b.done = %j', b.done); // 6, in a, b.done = true
exports.done = true;
console.log('a done'); // 7, a done

// b.js
console.log('b starting'); // 3
exports.done = false;
const a = require('./a.js');
console.log('in b, a.done = %j', a.done); // 4, in b, a.done = false
exports.done = true;
console.log('b done'); // 5, b done

// main.js
console.log('main starting'); // 1
const a = require('./a.js');
const b = require('./b.js');
// 8, in main, a.done=true, b.done=true
console.log('in main, a.done=%j, b.done=%j', a.done, b.done);
```

---

#### process

>  provides information about, and control over, the current Node.js process. As a global, it is always available to Node.js applications without using require().

```js
// process events, exit, beforeExit, disconnect, message, 
// rejectionHandled, uncaughtException, unhandledRejection ...
process.on('exit', () => {});

// signal event
process.stdin.resume();
process.on('SIGINT', () => {}); // SIGTERM, SIGINT, SIGBREAK, CTRL+C, SIGSTOP ...


// command line arguments
process.argv.forEach((val, index) => {});

// path
process.chdir('/tmp'); // changes the current working directory 
prcesss.cwd() // returns the current working directory
```

---

```js
// env, property returns an object containing the user environment
console.log(process.env); 

// exit process
// terminate the process as quickly as possible 
[process | Node.js v6.9.2 Documentation](https://goo.gl/uYDZDF)
process.exit(0);
process.abort(); // process exit immediately

// dedicate callback to queue
process.nextTick(() => {}); // method adds the callback to the "next tick queue"

```

---

#### setImmediate / setInterval / setTimeout

```js
// call at the end of this turn of Event Loop, after I/O event, before timer created
setImmediate(() => {});

// Schedules repeated execution of callback every delay milleseconds
var timer = setInterval(() => {}, 1000);
clearInterval(timer);

// Schedules execution of a one-time callback after delay milliseconds
// The callback will likely not be invoked in precisely delay milliseconds
var clearTimeout = setTimeout(() => {}, 1000);
clearInterval(timer);

```

---

### Javascript for Node.js

---

#### Register callback for asynchrous APIs

> In Node.js, Using `error-first`(`errorback`) callback priciple

```js
const fs = require('fs');

fs.stat('.', (err, stats) => {});
fs.unlink('/tmp/hello', err=> {});

const dns = require('dns');
dns.lookup('nodejs.org', (err, addresses, family) => {});

const net = require('net'); // TCP
var server = net.createServer((socket) => {});
```

---

#### Register event handler for event-driven APIs

```js
const net = require('net');

const server = net.createServer(s => {
  s.on('end', () => {
    console.log('client disconnected');
  });
  
  s.on('data', () => {});
});

```

---

#### Promise


- Alternative way to [callback hell](http://callbackhell.com/) for synchronous computations
- will be backed from `async` and `await`
- [pify](https://github.com/sindresorhus/pify)
  ```js
  const fs = require('fs');
  const pify = require('pify');

  // promisify a single function

  pify(fs.readFile)('package.json', 'utf8').then(data => {
      console.log(JSON.parse(data).name);
      //=> 'pify'
  });
  ```

---

### Core Modules

> os, fs, buffer, stream, child process

---

#### os

> provides a number of operating system-related utility methods

```js
const os = require('os');

console.log(os.EOL); // \n or \r\n
console.log(os.arch()); // CPU architecture
console.log(os.cpus()); // information about each CPU/core installed
console.log(os.homedir()); // return home directory
console.log(os.hostname()); // returns the hostname
console.log(os.platform()); // returns OS platform
console.log(os.tmpdir()); // returns path OS's default temp path
```

---

### fs, File System

>  provides a wrapper for the standard file operations

```js
const fs = require("fs");
var filename = "log.data";

fs.open(filename, 'r', (err, fd) => {
  if (err) {
    if (err.code === "EEXIST") {
      console.error('myfile already exists');
      return;
    } else {
      throw err;
    }
  }

  fs.stat(filename, (err, stats) => {
    console.log(stats);
    const buffer = new Buffer(stats.size);
    fs.read(fd, buffer, 0, stats.size, null, (err, bytesRead, buffer) => { });
  });
});
```

---

### Buffer

> manipulating streams of binary data by optimized Uint8Array API

```js
const buf = new Buffer('abcd');
console.log(buf[0]); // 97
console.log(buf.toString()); // abcd
console.log(buf.indexOf('a')); // 0
console.log(buf.length); // 4

const buf2 = Buffer.alloc(4); // <Buffer 00 00 00 00>
buf2.fill(1);
console.log(buf2); // <Buffer 01 01 01 01>

buf.copy(buf2); // copy buf to buf2
console.log(buf, buf2, buf2.equals(buf)); // true
console.log(buf2.slice(0, 1)); // 0x61

// byte read and write
console.log(buf2.readInt8(0), buf2.readInt8(1)); // 97 98
console.log(buf.write('ef', 0), buf.toString()); // efcd

// Class method
console.log(Buffer.byteLength(buf2)); // 5
console.log(Buffer.compare(buf, buf2)); // 0
```

---

### EventEmitter

> Node.js core API is built around an idiomatic asynchronous event-driven architecture in which certain kinds of emitter objects emit named events to liteners

```js
const EventEmitter = require('events');

class HTTP3 extends EventEmitter {
  request(msg) {
    if (!msg) { this.emit('request', new Error('no message')); return;}
    this.emit('request', null, msg);
  }
}

const http3 = new HTTP3();
http3.on('request', (err, msg) => {
  if (err) { throw err; }

  console.log('done with', msg);
});

http3.request('msg');
http3.request(); // will cause error
```

---

### Stream

![center](https://cloud.githubusercontent.com/assets/124117/21172352/c1824c74-c214-11e6-99aa-c7963213f423.png)

- Abstract interface for working with streaming data in Node.js inherited from EventEmitter
- Managing massive size stream data from network or file
	- TCP, HTTP requests / responses
	- fs write, zlib, crypto, streams
	- process.stdout, process.stderr, child process stdin
- Readable, Writable, [Duplex/Transform (both readable and writable)](http://stackoverflow.com/questions/18335499/nodejs-whats-the-difference-between-a-duplex-stream-and-a-transform-stream)

---

#### Transform

>  Duplex stream where the output is computed in some way from the input

```js
const Transform = require('stream').Transform;

class MyTransform extends Transform {
  constructor(options) {
    super(options);
  }
  
  transform(data, encoding, done) {
    // adter processing
    this.push(data);
    done();
  }
}
```
---

### Child Process

> provides the ability to spawn child processes

```js
const spawn = require('child_process').spawn;
const ls = spawn('ls', ['-lh', '/usr']);

ls.stdout.on('data', (data) => {
  console.log(`stdout: ${data}`);
});

ls.stderr.on('data', (data) => {
  console.log(`stderr: ${data}`);
});

ls.on('close', (code) => {
  console.log(`child process exited with code ${code}`);
});
```

---

#### handful of synchronous and asynchronous alternatives to child_process.spawn()

- **child_process.exec()**: spawns a shell and runs a command
- **child_process.execFile()**: spawns the command directly
- **child_process.fork()**: spawns a new Node.js process with specified module, IPC communication
- **child_process.execSync()**: a synchronous version of child_process.exec(), `will block the event loop`
- **child_process.execFileSync()**: a synchronous version of child_process.execFile() `will block the event loop`

---

#### child_process.exec

```js
const exec = require('child_process').exec;
exec('ls -al', (error, stdout, stderr) => { // shell wil be spawned
  if (error) {
    console.error(`exec error: ${error}`);
    return;
  }
  console.log(`stdout: ${stdout}`);
  console.log(`stderr: ${stderr}`);
});
```

##### child_process.execFile

```js
const execFile = require('child_process').execFile;
// run a file without running shell. It might work more efficiently
const child = execFile('node', ['--version'], (error, stdout, stderr) => {
  if (error) {
    throw error;
  }
  console.log(stdout);
});
```

---

### NPM for Node.js Projects

> Initializing, development and deploy with NPM

---

#### Finding

- `npm search` or npmjs.com/search?q=
- [Awesome Node.js, Delightful Node.js packages and resources](https://goo.gl/FUyIbb)
- [Nipster! npm search tool for Node.js](https://goo.gl/U3mDJL)
- [Libraries.io - The Open Source Discovery Service](https://goo.gl/eXUv9x)

---

#### Intializing for Node Projects

> All of setting will be save at [package.json](https://docs.npmjs.com/files/package.json)

```sh
npm init
```

#### Installing packages to the existing project

> Install all of the dependencies in package.json

```sh
npm install
```

---

#### Installing new packages as a dev/depedencies

> Install a new dependency to the project for development and production

```sh
// for production
npm install --save PACKAGE_NAME
npm i -S $PACKAGE_NAME

// for development
npm install --save-dev $PACKAGE_NAME
npm i -D $PACKAGE_NAME
```

#### Running NPM scripts for development

```sh
npm start
npm test
npm run $SCRIPT
```

#### Publish packages to NPM registry

```sh
npm publish
```

---

![3%](https://yarnpkg.com/assets/og_image.png)

> Rasing for solving big problems at Facebook and Google, gives us a lot of benefits

```sh
# init project
yarn init

# install packages of the project
yarn install

# install new package to depedencies
yarn add $PACKAGE_NAME

# install new package to dev depedencies
npm add --dev $PACKAGE_NAME

# run scripts
yarn start
yarn test
yarn run $SCRIPT
```

---

# Developing Node Applications

---

## Shell

```js
#!/usr/bin/env node
'use strict';

const fs = require('fs');
const exec = require('child_process').exec;
const cmd = process.argv.splice(2);

if (!cmd || cmd.length < 1) {
  console.error('Missing command');
  process.exit(-1);
}

exec(cmd.join(' '), (err, stdout, stderr) => {
  if (err) {
    console.error(err);
    return;
  }

  if (stdout) { console.log(stdout); }
  if (stderr) { console.log(stderr); }
});

```

---

## Web Server

```js
const http = require('http');
const index = `<html>
<head></head>
<body>
  <div>Hello</div>
</body>
</html>`;

const server = http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.end(index);
});

server.on('clientError', (err, s) => {
  socket.end('HTTP/1.1 400 Bad Request\r\n\r\n');
});

server.listen(8080, () => {
  console.log('Server has been started', server.address());
});
```

---

## Echo Server

```js
const net = require('net');
const server = net.createServer(s => {
  console.log('client connected');

  // handle closing connection
  s.on('end', () => {
    console.log('client disconnected');
  });

  // write welcome message
  s.write('hello\n\n');

  // echo message come from client
  s.pipe(s);
}).on('error', err => {
  throw err;
});

// to connect, telnet 0.0.0.0 8080, ctrl + ] + close to exit
server.listen({ port: 8080 }, () => {
  console.log('Server has been started', server.address());
});
```

---

# References

- [Morning Keynote- Everything You Need to Know About Node.js Event Loop - Bert Belder, IBM - YouTube](https://goo.gl/jrPvys)
- [UNIX System V Network Programming](https://goo.gl/iSx4I8)
- [Hyper termainal](https://github.com/zeit/hyper/releases) with [bash on Windows](https://github.com/zeit/hyper/issues/1020)
- [JSConf Budapest: what everybody should know about npm by seldo](https://goo.gl/OrxTMN)
- [Modulecounts](https://goo.gl/bgFoE)
- [Docs | Node.js](https://goo.gl/NHREqk)

---

# License

The content of this project itself is licensed under the [Creative Commons Attribution 3.0 license](http://creativecommons.org/licenses/by/3.0/us/deed.en_US), and the underlying source code used to format and display that content is licensed under the [MIT license](http://opensource.org/licenses/mit-license.php).