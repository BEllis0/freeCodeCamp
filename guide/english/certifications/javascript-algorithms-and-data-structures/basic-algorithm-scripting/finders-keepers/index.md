---
title: Finders Keepers
---

# Finders Keepers

---
## Problem Explanation
We need to return the element from an array that passes a function. Both the `function` and the `array` are passed into our function `findElement(arr, func)`.



---
## Hints

### Hint 1
We need to return the element from an array that passes a function. Both the `function` and the `array` are passed into our function `findElement(arr, func)`. Looking through the array can be done with a `for` loop.

### Hint 2
`num` is passed to the function. We will need to set it to the elements we want to check with the function.

### Hint 3
Do not forget, if none of the numbers in the array pass the test, it should return `undefined`.


---
## Solutions

<details><summary>Solution 1 (Click to Show/Hide)</summary>

```javascript
function findElement(arr, func) {
  let num = 0;

  for (var i = 0; i < arr.length; i++) {
    num = arr[i];
    if (func(num)) {
      return num;
    }
  }

  return undefined;
}
```

#### Code Explanation

* Challenge asks us to look through array. This is done using a `for` loop.
* The `num` variable is being passed into the function, so we set it to each index in our array.
* The pre-defined function already checks each number for us, so if it is "true", we return that num.
* If none of the numbers in the array pass the function's test, we return undefined.

</details>

<details><summary>Solution 2 (Click to Show/Hide)</summary>

```javascript
function findElement(arr, func) {

if (arr.filter(func).slice(0,1) <= 0) {
  return undefined;
}

else {
  return arr.filter(func).slice(0,1);
}

}
```

#### Relevant Links

*   [Array.prototype.filter](https://guide.freecodecamp.org/javascript/standard-objects/array/array-prototype-filter/)
*   [Array.prototype.slice](https://guide.freecodecamp.org/javascript/standard-objects/array/array-prototype-slice/)

#### Code Explanation

* Using the `filter` method, you can produce a new array which includes the numbers that pass the `func` test
* Adding `slice` to this, you can return the first number in the array
* The if statement tests if any numbers in the array pass the test by checking if a number greater than 0 was returned

</details>

<details><summary>Solution 3 (Click to Show/Hide)</summary>

```javascript
function findElement(arr, func) {
  return arr[arr.map(func).indexOf(true)];
}
```

#### Code Explanation

1. Look through the array given in the 1st paramater "arr" using the .map() method
2. Use the function in the 2nd parameter as the callback function in arr.map()
3. Acquire the index of the first number that meets the condition in the function.
4. Use that index to display the first available number that meets the condition.

</details>
