# Javascript Code Style
---
That's my code style for writing consistent and readable Javascript...

It was based on some great code style guides such from [Airbnb](https://github.com/airbnb/javascript) and [Idiomatic.js](https://github.com/rwaldron/idiomatic.js/).

Feel free to fork and create your own code style!

## Table of Contents
1. [Identation](#indentation)
1. [Strings](#strings)
1. [Semicolons](#semicolons)
1. [use strict](#usestrict)

## <a name='indentation'>Indentation</a>
Use **2** spaces... and never mix spaces and tabs.
```javascript
// Bad
if(true) {
∙∙∙∙console.log('Uou');
}
// Good
if(true) {
∙∙console.log('Yeah!');
}
```

## <a name='strings'>Strings</a>
Use single quotes `''` instead of double quotes `""`.
```javascript
// Bad
var foo = "Foo";

// Good
var foo = 'Foo';
```

## <a name='semicolons'>Semicolons</a>
Use it! no matter what people say about "You don't have to use semicolons in Javascript", it makes your code more readable, and in some cases, it can avoid some unexpected errors.
```javascript
// Bad :/
function() {
  console.log('Hey man, where are your semicolons?')
}

// Good!
function() {
  console.log('Hell Yeah!'); // <= use it!
}
```

## <a name='usestrict'>use strict</a>
Well, i like using it, it helps avoiding some common mistakes when writting javascript such as forgetting to declare a variable (this can be really harmful to your code).
```javascript
// it can be that way
(function() {
  // my code
});

// But i prefer like that
(function() {
  'use strict';
  // my code
});
```
