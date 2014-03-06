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
1. [Objects](#objects)
1. [Arrays](#arrays)
1. [Functions](#functions)
1. [Comments](#comments)
1. [JQuery](#jquery)

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

If your string is too long, break it into multiple lines... Also don't forget to indent those lines
```javascript
// super bad (awesome song)
var text = 'I came home Like a stone And I fell heavy into your arms These days of dust Which we\'ve known Will blow away with this new sun  And I\'ll kneel down Wait for now And I\'ll kneel down Know my ground  And I\'ll wait I will wait for you And I\'ll wait I will wait for you';

// super good
var text = 'I came home Like a stone And I fell heavy into your arms ' +
  'These days of dust Which we\'ve known Will blow away with this new sun ' +
  'And I\'ll kneel down Wait for now And I\'ll kneel down Know my ground ' +
  'And I\'ll wait I will wait for you And I\'ll wait I will wait for you';
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

Declare your variables in the beggining of the scope, it helps readability and can avoid some issues related to hoisting.
```javascript
// not good
function test() {
  console.log('Something');
  callSomeFunction();
  
  var myVar = true;
  
  return myVar;
}

// good
function test() {
  var myVar = true;

  console.log('Something');
  callSomeFunction(); 
  
  return myVar;
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

## <a name='objects'>Objects</a>
Use literal syntax to create objects.
```javascript
// Nah...
var myObj = new Object();

// :D
var myObj = {};

```

## <a name='arrays'>Arrays</a>
Use literal syntax to create arrays.
```javascript
// Nope...
var myArray = new Array();

// :D
var myArray = [];

```

Use Array.push to add items into the end of an array

```javascript
var myArray = [];

// Bad
myArray[myArray.length] = 'Hey friend';

myArray.push('Hey Friend!');

```

## <a name='functions'>Functions</a>
Never use ``arguments`` as a parameter of a function
```javascript
// never!
function hellNo(arguments) {
  // doing something
}

// that's the way i like it
function hellYeah(args) {
  // doing something
}
```

## <a name='comments'>Comments</a>
For multiline comments use ``/* ... */``, and for single line comments use ``// ...``
```javascript
// bad

// this is my
// multiline comment,
// and i should not use
// it like that
function nup() {
 /* this is my single line comment */
 console.log(':(');
}

// good

/**
 * This is my multiline comment
 * and this is way better
 * then the previous one
 */
function yep() {
  // this is a single line comment
  console.log(':)');
}
```
Note: i think all code should be readable as it is, and should not need comments for every single line of code... if you write something difficult to understand than you should comment the block in a general way, and not comment every single line explaining what everything is doing.

## <a name='jquery'>JQuery</a>
Cache your actions, and use ``$`` in front of a variable that is cached.
```javascript

// bad
(function() {
  $('.elem').fadeIn('fast');

  // some stuff

  $('.elem').fadeOut('fast');
} ());

// better
(function() {
  var elem = $('.elem');
  elem.fadeIn('fast');
  
  // stuff
  
  elem.fadeOut('fast');
} ());

// best
(function() {
  var $elem = $('.elem');
  $elem.fadeIn('fast');
  
  // stuff
  
  $elem.fadeOut('fast');
} ());
```

When using cascading with jquery, split it into multiple lines!
```javascript
$('.elem').fadeIn('fast').fadeOut('fast').show().hide(); // <- that's horrible to read!

$('.elem').fadeIn('fast');
  .fadeOut('fast')
  .show()
  .hide();
```

----
That's it for now... I'll keep implementing this doc, and feel free to fork!