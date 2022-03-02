# JavaScript Best Practices

## Avoid global variables as much as possible

Global variables can cause conflicts and thus errors.. 

[Global Variables Are Bad](http://wiki.c2.com/?GlobalVariablesAreBad)

## Code attribution/ plagiarism
- You're allowed to use code you found online (unless its license mentions otherwise)
- You should always credit the creator and source of used code
- For important pieces of code, include them in the acknowledgements at the bottom of your readme.
- For ALL code you haven't written, include the source in a comment right above the line where you use the code.
- If you base a project off of someone else's project, mention it explicitly in the code at the top of your file as well as in the readme.

## OOP versus functional approach
- You're allowed to commit to either strategy.
- [Here's a nice example of an OOP web app](https://github.com/TimTerwijn/web-app-from-scratch-1920). Notice how object are responsible and self contained. Also notice how you need to jump through the code a lot in order to follow the flow of control.
- [Tomas](https://github.com/TomasS666/web-app-from-scratch-1920/tree/master/docs) went for a more functional approach. Here it's easier to chain functionalities together and the code reads more like human language.

## Using InnerHTML
- InnerHTML is not safe when you're overwriting the entire html content of a node [citation needed]
- Don't pick an alternative because you saw it being used somewhere, read up on the differences and make an [informed decision](https://stackoverflow.com/a/7476723/5440366).

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

Or even better, take a look at the URL API:  
[MDN URL](https://developer.mozilla.org/en-US/docs/Web/API/URL)

## Keep functions simple and focused

Give functions one clear goal for better redability and reusability

[Functions and the Single Responsibility Principle](https://dev.to/eidorianavi/functions-and-the-single-responsibility-principle-48ae)

## Waterfall 🌊 vs. Returning Values 🎁

There are multiple ways of writing code, however that doesn't make this readable for everyone. Check this waterfall instance.

```js
// Waterfall code (ok) ❌
    // App.js
    import {cleanData} from 'Clean.js'
    function getData (){
        fetch('url',{})
            .then(res=>cleanData(res))
    }
    getData()
    // Render.js
    import {renderData} from 'Render.js'
    function cleanData (uncleanData){
        // clean data
        renderData(cleanedData)
    }
    // The Waterfall
    // getData() -> cleanData() -> renderData()
```

This piece of code requires you to search through multiple files and you're actually rendering with the `getData` function. This makes bug fixing and maintaining this way harder than it needs to be since it's unclear what is happening and where.
Instead it would be more efficient and readable if you let the functions return its values. You should always aim to make your code readable so that another developer can see what's happening in an instant.

```js
// Returning values (good) ⭕️
    // App.js
    import {getData} from 'Fetcher.js'
    import {cleanData} from 'Clean.js'
    import {renderData} from 'Render.js'

    function init async(){
        const data = cleanData(await getData())
        renderData(data)
    }
    init()
```
fetcher.js module
```js
    // 
    function getData (){
        // clean data
        return new Promise((resolve,reject)=>{
            fetch('url',{})
                .then(res=>resolve(res))
        })
    }
```

Make your code read like a book instead of the worst Ikea manual.

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

## Avoid inline CSS in JavaScript

Good:
```js
const el = document.querySelector('...');
el.classList.toggle('...');
```

Bad:
```js
const el = document.querySelector('...');
el.style.display('none');
```
For dynamic styling consider using custom properties, passing only data from JavaScript to CSS.
[It's Time To Start Using CSS Custom Properties](https://www.smashingmagazine.com/2017/04/start-using-css-custom-properties/)


## Loading external script files

Load external script files in the tail of the ```body``` element. Giving all DOM elements a chance to load before JavaScript kicks in.
You can also use asyn/defer attributes if you're feeling dandy!

[Asynchronous vs Deferred JavaScript](https://bitsofco.de/async-vs-defer/)

## Handle loaded state in .finally()

```js
state('loading')

  return fetch(url)
    .then(response => response.json())
    .then(data => clean(data.data))
    .then(data => store(data))
    .catch(err => {
      state(err)
    })
    .finally(()=> {
      state('loaded')
    })
```

[Promis finally method MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/finally)
