![typhonjs-core-backbone-events-logged](http://i.imgur.com/cbj8wYZ.png)

[![Backbone](https://img.shields.io/badge/backbone-1.2.3-yellowgreen.svg?style=flat)](https://github.com/jashkenas/backbone)
[![Documentation](http://js.docs.typhonrt.org/typhonjs/typhonjs-core-backbone-events-logged/badge.svg)](http://js.docs.typhonrt.org/typhonjs/typhonjs-core-backbone-events-logged/)
[![Code Style](https://img.shields.io/badge/code%20style-allman-yellowgreen.svg?style=flat)](https://en.wikipedia.org/wiki/Indent_style#Allman_style)
[![License](https://img.shields.io/badge/license-MPLv2-yellowgreen.svg?style=flat)](https://github.com/typhonjs-backbone/backbone-es6/blob/master/LICENSE)
[![Gitter](https://img.shields.io/gitter/room/typhonjs/TyphonJS.svg)](https://gitter.im/typhonjs/TyphonJS)

[![Build Status](https://travis-ci.org/typhonjs-backbone/typhonjs-core-backbone-events-logged.svg?branch=master)](https://travis-ci.org/typhonjs-backbone/typhonjs-core-backbone-events-logged)
[![Coverage](https://img.shields.io/codecov/c/github/typhonjs-backbone/typhonjs-core-backbone-events-logged.svg)](https://codecov.io/github/typhonjs-backbone/typhonjs-core-backbone-events-logged)
[![Dependency Status](https://www.versioneye.com/user/projects/56eb72704e714c0035e7647b/badge.svg?style=flat)](https://www.versioneye.com/user/projects/56eb72704e714c0035e7647b)

Provides a [typhonjs-core-logging](https://github.com/typhonjs-common/typhonjs-core-logging) enabled version of [typhonjs-core-backbone-events](https://github.com/typhonjs-backbone/typhonjs-core-backbone-events). Please refer to typhonjs-core-backbone-events documentation for usage details. 

TyphonLoggedEvents adds new functionality for triggering events. The following are new trigger mechanisms:

- `triggerDefer` - Defers invoking `trigger`.
- `triggerFirst` - Only invokes the first target matched and passes back any result to the callee.
- `triggerResults` - Invokes all targets matched and passes back an array of results in an array to the callee.
- `triggerThen` - Invokes all targets matched and adds any returned results through `Promise.all` which returns
a single promise to the callee.

[mainEventbus.js](https://github.com/typhonjs-backbone/typhonjs-core-backbone-events-logged/blob/master/src/mainEventbus.js) provides a standardized instance of TyphonLoggedEvents which serves as the name implies as a main eventbus. 

Enabling eventbus logging aids debugging. A notable addition to the API is the following methods:
- `setEventScrubber` - Sets a function which should accept one parameter which processes the `logData` object hash which is about to be sent to the logger. This is useful for scrubbing sensitive data such as username / password. 
- `setLogLevel` - Sets the log level used for logging output.
