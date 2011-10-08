# MoonScript for JavaScript

This is a version of [MoonScript](http://moonscript.org) that has been compiled to
JavaScript using [Emscripten](http://emscripten.org). 

## About

The Lua source code of MoonScript is concatenated into a single file which is
converted to a header using `xxd`. This is included a C file along with Lua and
LPeg which are then compiled into LLVM bitcode. Finally the entire thing is
linked and fed into Emscripten to create a JavaScript file.

The JavaScript is compressed with the [Closure
Compiler](http://code.google.com/closure/compiler/). The file itself takes a
long time to load, especially on Chrome, so it is loaded in as a [web
worker](https://developer.mozilla.org/en/Using_web_workers).

A simple HTML page creates the worker to provide an web interface for compiling
and running MoonScript.

Check it out at <http://moonscript.org/compiler>.

