## Advanced working with higher order function

1. Construct a function `objOfMatches` that accepts two arrays and a callback. `objOfMatches` will build an object and return it. To build the object, `objOfMatches` will test each element of the first array using the callback to see if the output matches the corresponding element (by index) of the second array. If there is a match, the element from the first array becomes a key in an object, and the element from the second array becomes the corresponding value.

```js
function objOfMatches(array1, array2, callback) {
  let obj = {};
  for(let i = 0; i < array1.length; i++) {
    if(callback(array1[i]) === array2[i]) obj[array1[i]] = array2[i];
  }
  return obj;
}

// TEST
console.log(
  objOfMatches(
    ['hi', 'howdy', 'bye', 'later', 'hello'],
    ['HI', 'Howdy', 'BYE', 'LATER', 'hello'],
    function (str) {
      return str.toUpperCase();
    }
  )
); // should log: { hi: 'HI', bye: 'BYE', later: 'LATER' }
```

2. Construct a function `multiMap` that will accept two arrays: an array of values and an array of callbacks. `multiMap` will return an object whose keys match the elements in the array of values. The corresponding values that are assigned to the keys will be arrays consisting of outputs from the array of callbacks, where the input to each callback is the key.

```js
function multiMap(arrVals, arrCallbacks) {
  let obj = {};
  arrVals.forEach(value => {
    obj[value] = arrCallbacks.map(cb => {
      return cb(value);
    })
  })
  return obj;
}

// TEST
console.log(
  multiMap(
    ['catfood', 'glue', 'beer'],
    [
      function (str) {
        return str.toUpperCase();
      },
      function (str) {
        return (
          str[0].toUpperCase() + str.slice(1).toLowerCase()
        );
      },
      function (str) {
        return str + str;
      },
    ]
  )
); // should log: { catfood: ['CATFOOD', 'Catfood', 'catfoodcatfood'], glue: ['GLUE', 'Glue', 'glueglue'], beer: ['BEER', 'Beer', 'beerbeer'] }
```

3. Construct a function `objOfMatchesWithArray` that accepts three arrays. First two array will be an array of same length. Third array is a collection of functions in an array. `objOfMatchesWithArray` will build an object and return it. Loot at the example below to understand better

To build the object, `objOfMatchesWithArray` will test each element of the first array through all the function in the third array one after another(The output of one function will become the input of another).

The final output from the third array will be matched agains the same indexed element of second array. If there is a match, the element from the first array becomes a key in an object, and the element from the second array becomes the corresponding value.

```js
function objOfMatchesWithArray(array1, array2, callback) {
  let obj = {};
  array1.forEach((element,index) => {
    let compare = callback.reduce((acc,fn) => {
      acc = fn(acc);
      return acc;
      }, element)
      if(compare === array2[index]) obj[element] = compare;
  })
  return obj;
}

// TEST
console.log(
  objOfMatchesWithArray(
    ['hi', 'howdy', 'bye', 'later', 'hello'],
    ['HiHi', 'HowdyHowdy', 'BYEBYE', 'LATER', 'helloHello'],
    [
      function (str) {
        return str.toUpperCase();
      },
      function (str) {
        return (
          str[0].toUpperCase() + str.slice(1).toLowerCase()
        );
      },
      function (str) {
        return str + str;
      },
    ]
  )
); // should log: { hi: 'HiHi', howdy: 'HowdyHowdy'}
```

4. Construct a function `objectWithArrayValues` that accepts two arrays. First array will be array of any values, second array will be array of functions.

To build the object, `objectWithArrayValues` will pass each value of the first array through all the function in the second array one after another.

In the final object the key will be the value form the first array like `hi` and value will be an array of values returned from each function like `['HI', 'Hi', 'HiHi']`

```js
function objOfMatchesWithArray(array1, callback) {
  let obj = {};
  array1.forEach((element,index) => {
    obj[element] = callback.map(fn => {
      return fn(element);
      })
  })
  return obj;
}

// TEST
console.log(
  objOfMatchesWithArray(
    ['hi', 'howdy', 'bye'],
    [
      function (str) {
        return str.toUpperCase();
      },
      function (str) {
        return (
          str[0].toUpperCase() + str.slice(1).toLowerCase()
        );
      },
      function (str) {
        return str + str;
      },
    ]
  )
); // should log: { hi: ['HI', 'Hi', 'hihi'], bye: ['BYE', 'Bye', 'byebye'], later: ['LATER', 'Later', 'laterlater'] }
```

5.

```js
function sayHi() {
  console.log('Hi');
}
function sayHello() {
  console.log('Hello');
}
function sayHey() {
  console.log('Hey');
}
```

Create a function named `schedule` which accept two arguments an array of functions like `[sayHi, sayHello, sayHey]` and array of seconds like `[1, 2, 3]`. Both array will be of same length. If that's not the case alert a message saying `invalid input`. (1 second is 1000 ms)

The function `schedule` will execute the function at first index after the value in value on first index in second array. i.e execute `sayHi` after `1` second and `sayHello` after `2` second.

```js
function schedule(fnArray, secArray) {
  if(fnArray.length !== secArray.length) {
    alert(`invalid input`);
  } else {
  fnArray.forEach((fn, index) => {
    setTimeout(fn, secArray[index] * 1000);
  })
  }
}

function sayHi() {
  console.log('Hi');
}
function sayHello() {
  console.log('Hello');
}
function sayHey() {
  console.log('Hey');
}
schedule([sayHi, sayHello, sayHey], [2, 3, 4]);

// sayHi will be executed after 2 seconds
// sayHello will be executed after 3 seconds
// sayHey will be executed after 4 seconds
```