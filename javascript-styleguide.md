# JavaScript Styleguide #

## Syntax ##

+ Use “[the one true brace style][1TBS]” with 2 space soft-tabs for indentation.
+ Follow the `if`, `else`, `for`, `while`, `try` and `function` keywords by a space.
+ Always use braces with the above-mentioned keywords, even when they only nest one statement.
+ End each statement with a semicolon.
+ Put a space on each side of an operator.

```js
// Bad
if (condition) doThis();

var hello = function() { /* ... */ }

hello=1+2;

// Good
if (condition) {
  doThis();
}

var hello = function () { /* ... */ }

hello = 1 + 2;
```

+ Use literal syntax for creating objects and arrays.
+ Do not use leading commas.
+ Do not add trailing comma.

```js
// Bad
var items = new Array();
var thing = new Object();

var collection = [
    'apple'
  , 'orange'
  , 'banana'
];

var car = {
  color: 'blue',
  rims: 'alloy',
};

//Good
var items = [];
var thing = {};

var collection = [
  'apple',
  'orange',
  'banana'
];

var car = {
  color: 'blue',
  rims: 'alloy'
};
```

+ Use single quotes for wrapping strings.

```js
// Bad
var color = "blue";

// Good
var color = 'blue';
```


## Variables ##

+ Always declare variables to avoid polluting the global namespace.
+ Declare each variable individually—it makes it easier to maintain.
+ Put variable declarations at the top of the local scope to avoid hoisting headaches.
+ Declare unassigned variables last.

```js
// Bad
thing = getThing();

var color = 'blue',
    size = 9;

var my_var;

// Good
var thing = getThing();

var color = 'blue';
var size = 9;

var myVar;
```


## Properties ##

+ Use dot notation when operating on object properties.
+ Use bracket notation when operating on properties that are invalid identifiers or when using variables.

```js
// Bad
object['quality'] = 'strong';
object.@you = true;

// Good
object.quality = 'strong';
object['@you'] = true;
```


## Conditional expressions ##

+ Prefer the use of `===` and `!==` instead of `==` and `!==`.
+ Use shortcuts when possible.

```js
// Bad
if (items.length > 0) { /* ... */ }
if (name !== '') { /* ... */ }

// Good
if (items.length) { /* ... */ }
if (name) { /* ... */ }
```


## Functions ##

+ Put function declarations at the top of their scope, second only to variable declarations.
+ Never declare a function inside of a non-function block such as `if`, `while` or `for`.

```js
// Bad
if (condition) {
  function example() { /* ... */ }
}

// Good
var example;
if (condition) {
  example = function () { /* ... */ }
}
```


## Naming conventions ##

+ Choose concise, but meaningful names.
+ Use camel case.
+ Capitalize names of functions that are to be used as constructors.

```js
// Bad
var c = 0;
var image_path;

function view() { /* ... */ }
var panel = new view();

//Good
var counter = 0;
var imagePath;

function View() { /* ... */ }
var panel = new View();

```


## Miscellaneous ##

+ When using `parseInt` for converting to integer always specify the radix.

```js
// Bad
var number = parseInt('123');

// Good
var number = parseInt('123', 10);
```



[1TBS]: http://en.wikipedia.org/wiki/Indent_style#Variant:_1TBS
