# Javascript Best Practices

## Avoid global variables as much as possible

Global variables can cause conflicts and thus errors.. 

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

Give a function one clear goal for better redability and reusability
