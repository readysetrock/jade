# [![Jade - Node Template Engine](http://garthdb.com/img/jade_branding/jade-01.svg)](http://jade-lang.com/)

Full documentation is at [jade-lang.com](http://jade-lang.com/)

 Jade is a high performance template engine heavily influenced by [Haml](http://haml.info/)
 and implemented with JavaScript for [node](http://nodejs.org) and browsers. For bug reports,
 feature requests and questions, [open an issue](https://github.com/jadejs/jade/issues/new).
 For discussion join the [chat room](https://gitter.im/jadejs/jade).

 You can test drive Jade online [here](http://naltatis.github.com/jade-syntax-docs).

 [![Build Status](https://img.shields.io/travis/pugjs/jade/master.svg?style=flat)](https://travis-ci.org/jadejs/jade)
 [![Coverage Status](https://img.shields.io/coveralls/jadejs/jade/master.svg?style=flat)](https://coveralls.io/r/jadejs/jade?branch=master)
 [![Dependency Status](https://img.shields.io/david/pugjs/jade.svg?style=flat)](https://david-dm.org/jadejs/jade)
 [![devDependencies Status](https://img.shields.io/david/dev/pugjs/jade.svg?style=flat)](https://david-dm.org/jadejs/jade#info=devDependencies)
 [![NPM version](https://img.shields.io/npm/v/jade.svg?style=flat)](https://www.npmjs.com/package/jade)
 [![Join Gitter Chat](https://img.shields.io/badge/gitter-join%20chat%20%E2%86%92-brightgreen.svg?style=flat)](https://gitter.im/jadejs/jade?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Installation

via npm:

```bash
$ npm install jade
```

## Syntax

Jade is a clean, whitespace sensitive syntax for writing html.  Here is a simple example:

```jade
doctype html
html(lang="en")
  head
    title= pageTitle
    script(type='text/javascript').
      if (foo) bar(1 + 5)
  body
    h1 Jade - node template engine
    #container.col
      if youAreUsingJade
        p You are amazing
      else
        p Get on it!
      p.
        Jade is a terse and simple templating language with a
        strong focus on performance and powerful features.
```

becomes


```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Jade</title>
    <script type="text/javascript">
      if (foo) bar(1 + 5)
    </script>
  </head>
  <body>
    <h1>Jade - node template engine</h1>
    <div id="container" class="col">
      <p>You are amazing</p>
      <p>Jade is a terse and simple templating language with a strong focus on performance and powerful features.</p>
    </div>
  </body>
</html>
```

The official [jade tutorial](http://jade-lang.com/tutorial/) is a great place to start.  While that (and the syntax documentation) is being finished, you can view some of the old documentation [here](https://github.com/jadejs/jade/blob/master/jade.md) and [here](https://github.com/jadejs/jade/blob/master/jade-language.md)

## API

For full API, see [jade-lang.com/api](http://jade-lang.com/api/)

```js
var jade = require('jade');

// compile
var fn = jade.compile('string of jade', options);
var html = fn(locals);

// render
var html = jade.render('string of jade', merge(options, locals));

// renderFile
var html = jade.renderFile('filename.jade', merge(options, locals));
```

### Options

 - `filename`  Used in exceptions, and required when using includes
 - `compileDebug`  When `false` no debug instrumentation is compiled
 - `pretty`    Add pretty-indentation whitespace to output _(false by default)_

## Browser Support

 The latest version of jade can be download for the browser in standalone form from [here](https://raw.githubusercontent.com/jadejs/jade/1.11.0/jade.js).  It only supports the very latest browsers though, and is a large file.  It is recommended that you pre-compile your jade templates to JavaScript and then just use the [runtime.js](https://raw.githubusercontent.com/jadejs/jade/1.11.0/runtime.js) library on the client.

 To compile a template for use on the client using the command line, do:

```console
$ jade --client --no-debug filename.jade
```

which will produce `filename.js` containing the compiled template.

## Command Line

After installing the latest version of [node](http://nodejs.org/), install with:

```console
$ npm install jade -g
```

and run with

```console
$ jade --help
```

## Additional Resources

Tutorials:

  - cssdeck interactive [Jade syntax tutorial](http://cssdeck.com/labs/learning-the-jade-templating-engine-syntax)
  - cssdeck interactive [Jade logic tutorial](http://cssdeck.com/labs/jade-templating-tutorial-codecast-part-2)
  - [Jade について。](https://gist.github.com/japboy/5402844) (A Japanese Tutorial)
  - [Jade - 模板引擎](https://github.com/jadejs/jade/blob/master/Readme_zh-cn.md)

Implementations in other languages:

  - [php](https://github.com/kylekatarnls/jade-php)
  - [scala](http://scalate.fusesource.org/versions/snapshot/documentation/scaml-reference.html)
  - [ruby](https://github.com/slim-template/slim)
  - [python](https://github.com/SyrusAkbary/pyjade)
  - [java](https://github.com/neuland/jade4j)

Other:

  - [Emacs Mode](https://github.com/brianc/jade-mode)
  - [Vim Syntax](https://github.com/digitaltoad/vim-jade)
  - [TextMate Bundle](http://github.com/miksago/jade-tmbundle)
  - [Coda/SubEtha syntax Mode](https://github.com/aaronmccall/jade.mode)
  - [html2jade](https://github.com/donpark/html2jade) converter
  - [jade2php](https://github.com/SE7ENSKY/jade2php) converter
  - [Jade Server](https://github.com/ded/jade-server)  Ideal for building local prototypes apart from any application

## License

MIT
