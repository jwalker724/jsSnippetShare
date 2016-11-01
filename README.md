# jsSnippetShare
An place to share JavaScript tips tricks and snippets. The goal is to build this out so it can be a quick reference with reusable easy to understand examples.

### Code Snippets
* [isRequired] - Form field validation class that verifies if a field is populated and if it is required and populated based on another field value (optional)
* [Performance analysis] - Using console.time and console.timeEnd we can check or compare the performance of an operation.

### Tips & Tricks

##### every() method

The .every() method can be used to run a function or test on every element in the array
```sh
// syntax
array.every(callback)
```
```sh
// Examples:
// Test the every element in the array is greater than or equal to 5
[72, 5, 8, 30, 44].every(e => e >= 5); // returns true
[72, 5, 8, 3, 44].every(e => e >= 5); // returns false

// Same test using external callback function
function isGTEfive(element) {
  return element >= 5;
}
[72, 5, 8, 30, 44].every(isGTEfive); // returns true
[72, 5, 8, 3, 44].every(isGTEfive); // returns false
```

##### Short circuting with 'OR' logic

To set a variable to one thing if it is defined, but a default value if it is not.
```sh
// using or logic
var goodDay = sunShine || not
```
```js
// without or logic (old way)
var goodDay = not;
if (sunShine) {
  var goodDay = sunShine;
}
```

##### Ternary operator

Single line if expression

```sh
// syntax
condition ? expr1 : expr2
```
```js
// example
"Total price is " + (isMember ? "$5.00" : "$25.00");
```

##### Double Tilde

The double tilde can be used as a quick way to truncate a value to an integer.
It's nice because it never returns NaN. If it fails, it just returns 0.

```js
console.log( ~~15.02 );    // returns 15
console.log( ~~"45.81" );  // returns 45
console.log( ~~-5.8 );     // returns -5
console.log( ~~"car" );    // returns 0
console.log( ~~[] );       // returns 0
console.log( ~~null );     // returns 0
```

### Contributing ##
This is an open source project and your contributions are welcomed and encouraged.

- Fork this repository
- For code snippets: (see Style-Guide)
   - add a markdown file to the src folder containing the JavaScript code
   - add a short clear descriptive to the "Code Snippets" section section in the `readme.md` file.
- For short informational Tips & Tricks (see Style-Guide)
   - add a short clear descriptive title followed by the Tip or Trick to the "Tips & Tricks" section in the `readme.md` file.
- Add your name to the "contributors" section in the `package.json` file.
- Submit a Pull Request

### Style-Guide ###
Please follow this simple style-guide for all code contributions:

* Indent using spaces.
* camelCase all callables.
* Use semi-colons.
* Place a space after a conditional or function name, and its conditions/arguments. `function (...) {...}`
* Make sure to include comments
* Tips & Tricks should be no more than a pargraph or two, longer Tips & Tricks should be moved to a Code Snippets

[isRequired]: <https://github.com/jwalker724/jsSnippetShare/blob/master/src/isrequired.md>
[Performance analysis]: <https://github.com/jwalker724/jsSnippetShare/blob/master/src/performance.md>
