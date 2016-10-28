## Performance analysis
Using console.time and console.timeEnd we can check or compare the performance of an operation.
In the example below we convert a nodelist to an array and compare the conversion methods using performance analysis.
```html
/** HTML - add elements for the selector to access */
<input type="checkbox" name="test" value="1" class="myCheckBoxes" />
<input type="checkbox" name="test" value="2" class="myCheckBoxes" />
...
<input type="checkbox" name="test" value="100" class="myCheckBoxes" />
```
```js
/** returns a nodelist of elements with the myCheckBoxes CSS class */
var elementList = document.querySelectorAll('.myCheckBoxes');

/** For Loop Method  */
console.time('For Loop Method'); // start timer
  var array1 = [], i=0;;
    for (i=0; i < elementList.length ; i++) {
    array1[i] = elementList[i];
  };
console.timeEnd('For Loop Method'); // end timer

/** Slice Call Method */
console.time('Slice Call Method'); // start timer
  var array2 = Array.prototype.slice.call(elementList);
console.timeEnd('Slice Call Method'); // end timer
```
```js
/** Results */
For Loop Method: 0.753ms
Slice Call Method: 0.331ms
```
