# Javascript Best Practices

## Avoid global variables as much as possible

Global variables can cause conflicts and thus errors.. 

[Global Variables Are Bad](http://wiki.c2.com/?GlobalVariablesAreBad)

## Cache elements in variables

For readability and efficient code. Only one lookup is needed when the element is stored in a variable.

Good:
```js
const el = document.querySelector('...');
el.classList.toggle('...');
```

Bad:
```js
document.querySelector('...').classList.toggle('...');
```

## Split fetch url in separate chunks

For readability and efficient code. With this aproach parts of the url can be reused for future fetches.

Good:
```js
const cors = 'https://cors-anywhere.herokuapp.com/';
const endpoint = 'https://api.anywhere.com';
const key = '42';
const url = `${cors}`${endpoint}/?key=${key};

fetch (url) 
```

Bad:
```js
fetch('https://cors-anywhere.herokuapp.com/https://api.anywhere.com?key=42');
```

## Keep functions simple

Give functions one clear goal for better redability and reusability

## DRY

Don't repeat yourself!

For efficient and readable code.

[DRY code vs. WET code](https://www.codementor.io/@joshuaaroke/dry-code-vs-wet-code-89xjwv11w)

## var, let or const?
Know when to use which assignment identifier. Be consitent and try to make the most logical choices for your code.

[JavaScript ES6+: var, let, or const?](https://medium.com/javascript-scene/javascript-es6-var-let-or-const-ba58b8dcde75)


## for versus forEach

In most cases a forEach loop is a better choice for looping through an array(like object). 

[forEach vs for Loops in JavaScript: What's the Difference?](https://alligator.io/js/foreach-vs-for-loops/)

