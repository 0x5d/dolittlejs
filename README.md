# dolittle.js
Dolittle kindly translates your camelCase JSON object keys into snake_case keys, and viceversa.
It's meant to minimize the effort in translating camel case JSON keys of JS
clients to snake case, used in some APIs made with Ruby, for example.

## Install it with npm or bower
```sh
$ bower install dolittle
```
```sh
$ npm install dolittle
```
### Angular module:
For the angular module, go [here](https://github.com/castillobg/dolittle).

## Use it
```javascript
var dolittle = require('dolittle');

var testObj = {
  helloWorld : 'Hello World',
  nestedObject : {
    danger : 'Here be dragons',
    fooBar : [1, 2, 3],
    fooBarBaz : [
      { test1 : 'what'},
      { test2 : ['this', 'that']}
    ]
  }
};

var snakeized = dolittle.to.snake(testObj);
// will return:
// {
//   "hello_world" : "Hello World",
//   "nested_object" : {
//     "danger" : "Here be dragons",
//     "foo_bar" : [1,2,3],
//     "foo_bar_baz" : [
//       {"test1" : "what"},
//       {"test2" : [ "this","that"]}
//     ]
//   }
// }

var camelized = dolittle.to.camel(snakeized);
// will return the original object.
```
