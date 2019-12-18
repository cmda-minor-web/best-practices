# A collection of best practices used in the minor web

## General Coding
Code should be easily readable. Most of our best practices stem from this golden rule

- Useful shorthands that implicitly execute logic like the spread operator `[...myArray]` will not be used by teachers unless explicitly explained in class.
- Students can use shorthands if and only if they deeply understand the difference between two methods. Any problems resulting from a deviation from the teacher's norm are your own to solve. 
  - E.g. if you write `arr2 = [...arr1]` you should know this has a different result then when you write `arr2 = arr1` for `arr1 = [1,2,3]`
- Avoid chaining logic on the same line. Break up code if that makes it more readable. 
  - TODO:add example
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


## Giving Feedback

## Asking Questions

## Accessibility

