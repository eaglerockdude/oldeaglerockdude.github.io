---
layout: page
title: Javascript
---

<p>
In addition to Rails and Ruby, this blog is about javascript.  As you know, ROR is the domain of the "back-end" and while you can accomplish javascript
type things with a templating language(ajax, buttons, you name it) the bottom line is everything is moving to javascript and related frameworks.  In particular,
Node.js, which is a framework with a non-blocking I/O event model. Ever since I read about HTML5/Websockets, I figured
the lifetime or ROR was limited...well hope not! Basically it's much faster with big loads.  I would think however
that only the biggest of companies(Walmart etc) would really need this kind of performance.  For the vast majority
of websites, a framework like ROR will suffice.
</p>
<p>
In my mind no developer should be without an understanding of this movement as javascript exists in every browser and web application in existence.
</p>

## Areas of interest

* Node Node Node

## NodeJS
General notes on NodeJS which gets its teeth from being a "non-blocking" framework.

### Modules
In any large development project code(context javascript) organization and in particular *scope control* is a best practice.  The Nodejs paradigm makes heavy use of
modules.

The CommonJS specification is used by node to organize modules and control scope.  Modules can be single files or many modules packaged up.

Code Example assuming module name we need to access is string_util.js with a constructor named StringUtil.  In node a module
is simply a file.

```javascript
module.exports = new StringUtil();
```
(You could also export the constructor, and create it in a separate step in the require module).

The module.exports exposes all of the functionality of the string_util.js API

To use/reference the API of this module, you require it.

```javascript
var strUtil = require("./string_util")
```
Node.js supports three main types of modules: core modules, user modules, and third-party modules.


This is a simple illustration.  There is much more to modules which can be found at [Node Module Documentation](https://nodejs.org/api/modules.html)

### Node Package Manager (NPM)
Node.js has a way of browsing, querying, installing, and publishing third-party modules into a central repository,
 and it's called NPM. NPM stands for Node Package Manager, and it consists of two things:

- A module repository that is fully browsable, accessible at [https://npmjs.org](https://npmjs.org).  And
- A command-line utility

The NPM repository contains a vast and growing collection of modules that were built by the community.
 Since that repository is fully browsable and searchable, you can use it to track down and inspect modules
 that may be interesting for building your application with.

### package.json
Node uses this json file as a manifest similar to how rails uses a GEMFILE. It declares what modules your app
needs, and NPM will use with *NPM install*.  NPM will analyze the modules and their dependencies, and download
them. (Example)

```json
{
    "name": "my-example-app",
    "version": "0.1.0",
    "dependencies": {
        "request": "*",
        "nano": "3.3.x",
        "async": "~0.2"
    }
}
```
By default, NPM installs the dependencies locally inside a directory named *Node_modules*. Node.js will look for this directory
when you use *require(module name)* and will look for the module there.

### The callback pattern

Here is a very common callback pattern used in Node.  Its an example of reading a file, and also checking for an error. In
the Node case, the result gets executed by the callback when its ready.  The callback is always the last parm.

Blocking IO

```javascript
try {
    var result = query('SELECT * FROM articles');
    console.log('result:', result);
} catch(err) {
console.error('error while performing query:', err.message);
}
```

Non-IO-Blocking with callback last parm

```javascript
query('SELECT * FROM articles', function(err, result) {
    if (err) {
        console.error('error while performing query:', err.message);
    } else {
        console.log('result:', result);
    }
});
```
The callback expects an error as the first argument, which is nil is there is no error. If there is an
error, it is a javascript err object.
