# Acorn Dirigible Module

[![Eclipse License](http://img.shields.io/badge/license-Eclipse-brightgreen.svg)](LICENSE)
[![GitHub contributors](https://img.shields.io/github/contributors/dirigiblelabs/ext-acorn.svg)](https://github.com/dirigiblelabs/ext-acorn/graphs/contributors)

A tiny, fast JavaScript parser written in JavaScript and packaged as a Dirigible module.

## Useage
```javascript
var acorn = require("acornjs/acorn");
var response = require("http/v4/response");

var code = [
  "var x = 5;",
  "var y = 10;",
  "var result = sum(x, y);",
  "",
  "/** Returns the sum of a and b",
  " */",
  "function sum(a, b) {",
  " return a + b;",
  "}"
].join("\n");

var comments = [];
var nodes = acorn.parse(code, {
    onComment: comments
});

var result = {
    nodes: nodes,
    comments: comments
};

response.println(JSON.stringify(result));
```

> For more details go to the original repo: [acornjs/acorn](https://github.com/acornjs/acorn/tree/master/acorn)

## License

This project is copyrighted by [SAP SE](http://www.sap.com/) and is available under the [Eclipse Public License v 1.0](https://www.eclipse.org/legal/epl-v10.html). See [LICENSE](LICENSE) and [NOTICE.txt](NOTICE.txt) for further details.
