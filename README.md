# Traversal
By Ryan Sandor Richards

## Installation
`npm install traversal`

## Introduction

The [tree traversal](http://en.wikipedia.org/wiki/Tree_traversal) is a fundamental problem in computer science and it occurs in many contexts (e.g. compilers). This library aims to make them easier to write and read in JavaScript.

## Usage

Traversal works by holding the computational state of a tree traversal in the form of an JavaScript class. The library exposes a single factory method, `traversal()`, that creates a new instance and allows you to override its default behaviors.

Here's an example of how it might be used:

```js
// 1. Require the library
var traversal = require('traversal');

// 2. Format a tree using nest objects
var myTree = {
  name: 'root',
  left: {
    name: 'left child'

  },
  right: {
    name: 'right child'
  }
};

// 3. Build a traversal that prints out node names and
//    recursively follows the `left` and `right` properties.
var logger = traversal()
  .visit(function(node) { console.log(node); })
  .preorder('left', 'right');

// 4. Execute the traversal by calling `walk`
logger.walk(myTree);
```

This particular traversal would output the following:

```
root
left child
right child
```

## Documentation

Markdown documentation for the library is coming soon. For now you can fork and build the jsdoc documentation by running `npm install && npm run docs`. Then open the `docs/index.html` file in a web browser.


## License
MIT
