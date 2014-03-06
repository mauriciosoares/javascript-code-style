# Javascript Code Style

That's my code style for writing consistent and readable Javascript...

It was based on some great code style guides such from [Airbnb](https://github.com/airbnb/javascript) and [Idiomatic.js](https://github.com/rwaldron/idiomatic.js/).

Feel free to fork and create your own code style!

I'm sorry for the order of the content, I'll write everything and then organize it :)

## Table of Contents
1. [Identation](#indentation)
1. [Strings](#strings)
1. [Semicolons](#semicolons)
1. [use strict](#usestrict)
1. [Variables](#variables)
1. [Naming Conventions](#namingconventions)

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
Use single quotes `' '` instead of double quotes `" "`.
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

## <a name='variables'>Variables</a>
**Always declare your variables**, it can avoid some problems such as declaring it in the global scope.

```javascript
function() {
  // really bad :/
  imGlobal = true;

  // That's good
  var imNotGlobal = true;
}
```

## <a name='namingconventions'>Naming Conventions</a>
There are some patterns I like to follown when naming my variables and functions...

- **Common variables**: Use camel case for those... And one **important thing** is that your variable should be as short as it can be, but as long as necessary, so it can be readable and understandable.

```javascript
// nahh
var this_is_my_variable;

// better. but still too long
var thisIsMyVariable;

// wow, that's way better
var myVariable;

// that's it!
var myVar;
```
The point is that all of these can be read and understandable, but `myvar` is the best approach for this situation.

- **Constants**: Use uppercase for writting constant variables.

```javascript
// Nope my friend
var Pi = Math.PI;

// Wow!
var PI = Math.PI;
```

- **Classes**: Use Capital Letter for writting classes, its a pattern followed by a lot of other programming languages, and you can easily detect that it is a Class.

```javascript
// it works, but...
function person(name) {
  this.name = name;
}

var alan = new person('Alan');

// That's some good stuff!
function Person(name) {
  this.name = name;
}

var mauricio = new Person('Mauricio');
```