# A collection of best practices used in the minor web

## General Coding
Code should be easily readable. Most of our best practices stem from this golden rule

- Useful shorthands that implicitly execute logic like the spread operator `[...myArray]` will not be used by teachers unless explicitly explained in class.
- Students can use shorthands if and only if they deeply understand the difference between two methods. Any problems resulting from a deviation from the teacher's norm are your own to solve. 
  - E.g. if you write `arr2 = [...arr1]` you should know this has a different result then when you write `arr2 = arr1` for `arr1 = [1,2,3]`
- Avoid chaining logic on the same line. Break up code if that makes it more readable. 
  - TODO:add example
- Try to avoid chaining multiple fuctions and using unclear function names.
  - When you start chaining multiple functions your code tends to become spaghetti fast. When your code does this it's probably quite difficult for others to understand since he/she needs to dig through a lot of code to find where things happen. Expecially when you divvy up your code in modules or have a long file.
  <details>
    <summary> Example </summary>
  
    ```javascript
      process()

      // Other file/module
      function process(){
        // Does stuff
        render(data)
      }
    ```
    You don't know where `render` is called until you've explored the code. In more complex cases this becomes an even bigger mess. Instead it could be better to let functions return it's data and of course always keep clear function names.
    ```javascript
      rendersData(processData())

      // Other file/module
      function processData(){
        // Does stuff
        return data
      }
      function renderData(data){
        // renders stuff
      }
    ```
    This way you see what a function is supposed to do upfront without digging into the code.
  </details>
  - Appart from this, you should always try to let a function only do 1 thing. With the previous point in mind the code could be easier to reuse and distribute.

- Stick to a code style you understand and can apply consistently. 
  - If you learn how to use `myArray.map` instead of `for (var i in myArray)`, apply that code style to your whole project. 
  - If someone "helps" you by writing a piece of code in a different or more complex style than you're used to. Always convert it to your own style right away.
- Add code comments when either you or someone else might have trouble understanding what a piece of code does.
  - TODO: More detailed advice here 

### Naming Conventions


- Use descriptive variable and function names
  - `locationMarker` instead of `lm`
- Only abbreviate words when instantly understandable
  - `info` instead of `information` is fine but `locMark` instead of `locationMarker` takes more time to understand and should be avoided.

[JavaScript naming conventions](https://www.robinwieruch.de/javascript-naming-conventions)

### Git
Commit early and often

[Git best practices](https://sethrobertson.github.io/GitBestPractices/)





