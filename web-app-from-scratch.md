# Best Practices for WAFS

## Don't Repeat Yourself (DRY)
Your code should not repeat itself multiple times. When you have two pieces of code that are very similar, ask yourself how the code could be written in a dynamic, DRY way.

[Example](https://stackoverflow.com/a/31218286/5440366)

## Put your `<script src="script.js"></script>` tag before the closing tag `</body>`
I you place your script tag in the head of your document, you could run into problems where your Javascript is rendered earlier than your HTML.

## Keep the Global Scope clean

## Plan your code with Pseudo Code
It can help to write out a plan to build your work. Pseudo coding your work can help with that. 
* Decide what your goal will be
* write out step by step what you will build
* follow the plan
`
// goal: Render a random title

// fetch data from an API

// get render position in domain

// create a random number

// render a title from the API with the random number
`

## Element.setAttribute() vs Element.classList.add()
You should use the classList.add() & classList.remove() methods over .setAttribute() for working with HTML Element classes in Javascript. This has performance benefits as seen in the benchmark and allows for adding and removing multiple classes in one call.    
[MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)    
[Benchmark](https://measurethat.net/Benchmarks/ShowResult/93474)    

