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
