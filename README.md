# Require Module Support README

[![Build Status](https://api.travis-ci.org/anacierdem/vscode-requirejs.svg?branch=master)](https://travis-ci.org/anacierdem/vscode-requirejs)
[![JavaScript Style Guide: Good Parts](https://img.shields.io/badge/code%20style-goodparts-brightgreen.svg?style=flat)](https://github.com/dwyl/goodparts "JavaScript The Good Parts")
[![codecov](https://codecov.io/gh/anacierdem/vscode-requirejs/branch/master/graph/badge.svg)](https://codecov.io/gh/anacierdem/vscode-requirejs)
[![dependencies Status](https://david-dm.org/anacierdem/vscode-requirejs/status.svg)](https://david-dm.org/anacierdem/vscode-requirejs)
[![devDependencies Status](https://david-dm.org/anacierdem/vscode-requirejs/dev-status.svg)](https://david-dm.org/anacierdem/vscode-requirejs?type=dev)

## Features

Provides goto definition functionality for require js modules.

You can navigate to the source file from locations marked with the caret (^);

    require('moduleA').foo();
                ^       ^

    require(['moduleA', 'moduleB'], function(a, b) {
                ^           ^                ^  ^
        var foo = a;
             ^    ^  
        var bar = b;
             ^    ^
        foo.baz();
          ^  ^
        bar.prop;
         ^    ^
    });

    define('myName', ['moduleA', 'moduleB'], function(a, b) {
                          ^  	     ^                ^  ^
        var foo = new a();
             ^        ^  
        foo.bar();
         ^   ^
    });

## Settings

You can set module path relative to workspace root with 

    "requireModuleSupport.modulePath" 

without leading and trailing slashes.

Example;

    {
        "requireModuleSupport.modulePath": "modules"
    }

This will translate to `[WORKSPACE_ROOT]\modules`

It will default to workspace root path if not given.
You can also use relative paths on require/define calls.

Another option is;

    "requireModuleSupport.onlyNavigateToFile"

When set to true, it will prevent the final search in the landing module and instead just reference the file. When this feature is left as false, the constructor or property that the goto definition operation has started with will be searched in the module file.

## Support

The project is maintained at: [gitHub](https://github.com/anacierdem/vscode-requirejs)
Support me at http://patreon.com/anacierdem