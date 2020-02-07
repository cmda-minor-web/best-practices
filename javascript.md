# Javascript Best Practices

## Avoid global variables as much as possible

Global variables can cause conflicts and thus errors.. 

## Cache elements in variables for readability

Good:
```js
const el = document.querySelector('...');
el.classList.toggle('...');
```

Bad:
```js
document.querySelector('...').classList.toggle('...');
```
