# xom
[![TravisCI](https://img.shields.io/travis/kroogs/xom.svg)](https://travis-ci.org/kroogs/xom)
[![Coverage](https://img.shields.io/coveralls/kroogs/xom.svg)](https://coveralls.io/github/kroogs/xom)
[![Dependencies](https://img.shields.io/david/kroogs/xom.svg)](https://david-dm.org/kroogs/xom)
[![Dev Dependencies](https://img.shields.io/david/dev/kroogs/xom.svg)](https://david-dm.org/kroogs/xom?type=dev)
[![npm version](https://img.shields.io/npm/v/xom.svg)](https://www.npmjs.com/package/xom)
[![MIT License](https://img.shields.io/github/license/kroogs/proto-es2017.svg)](https://github.com/kroogs/xom/blob/master/LICENSE)

> Build DOM trees by misusing Proxy!

## Features

  - Dynamic wrapper for document.createElement and document.createElementNS.
  - Use HTML or JavaScript attribute names.
  - Automatically wrap other arguments in document.createTextNode.

## Install

  ```
  npm install --save xom
  ```

## Usage

  Basic package usage:
  ```javascript
  import { dom } from 'xom'
  const { div, span, b, i } = dom

  document.appendChild(
    div({className: 'banana'},
      span('ba', b('na'), i('na'))
    )
  )
  ```

  Customize Xom:
  ```javascript
  import { Xom } from 'xom'

  class MyXom extends Xom {}
  const x = MyXom.proxy()

  document.appendChild(
    x.div({className: 'banana'},
      x.span('ba', x.b('na'), x.i('na'))
    )
  )
  ```

## Why?

It was one of the ways of using [Proxy](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy)
that struck me. There are better solutions for most situations.
