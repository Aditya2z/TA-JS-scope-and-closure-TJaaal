1. Convert the function below into different forms of function expression.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}

// Your code goes here
let percentage = function (marks, total) {
  return (marks * 100) / total;
}

let percentage = (marks, total) => {
  return (marks * 100) / total;
}
```

2. Write Function Declaration or Function Expression next to the function.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}
// Your answer
//Function Declaration
```

```js
let percentage = function percentage(marks, total) {
  return (marks * 100) / total;
};
//Function Expression
```

```js
let percentage = function (marks, total) {
  return (marks * 100) / total;
};
//Function Expression
```

```js
let percentage = (marks, total) => {
  return (marks * 100) / total;
};
//Function Expression
```

```js
let percentage = (marks, total) => (marks * 100) / total;
//Function Expression
```

3. Why is a function definition an expression in JavaScript? Give one example of function expression.
In JavaScript, a function definition is considered an expression because it can be assigned to a variable or passed as an argument to another function, just like any other expression.
```js
const addNumbers = function (a, b) {
  return a + b;
};
```

4. Why is a function call an expression in JavaScript?
In JavaScript, a function call is considered an expression because it evaluates to a value. When a function is called, it executes the code inside the function and returns a value. This value can be assigned to a variable or used in other expressions.

5. Write VALID and INVALID next to each example below with the reason.

```js
function add(a, b) {
  return a + b;
}

let five = add(2, 3); // Answer VALID
five = add; // Answer VALID
five = five(10, 11); // Answer VALID
five = function () {
  return 'Hello';
}; // Answer VALID
```

6. What is the difference between function definition and function call? Explain with an example.
a function definition is the code that defines the function, while a function call is the code that executes the function.

7. What is the similarities between function definition and function call?
both function definition and function call can involve passing arguments. When defining a function, you specify the parameters that the function accepts. When calling a function, you provide the values for those parameters.

8. Is the code below valid or invalid. Explain with reason.

```js
function hello() {
  console.log('Hello World!');
}

hello.user = 'Sam'; //valid, Functions in JavaScript are objects and can have properties, but it is generally not recommended to add properties to functions in this way as it can make the code less readable and harder to maintain.
```

9. What is higher order function explain with an example.
 a higher-order function is a function that either takes one or more functions as arguments, or returns a function as its result. This means that a higher-order function either operates on functions or returns a function.
 ```js
 function multiplyBy(factor) {
  return function (number) {
    return number * factor;
  }
}

const double = multiplyBy(2);
const triple = multiplyBy(3);

console.log(double(5)); // Output: 10
console.log(triple(5)); // Output: 15
```

10. Explain what is callback function. Why you can pass a function inside a function?
a callback function is a function that is passed as an argument to another function, and is invoked by that function at a later time. The idea of a callback function is to provide a way for one function to "call back" to another function when a certain task is complete.