Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

Example:

```js
function hello() {
  var username = 'Arya';
}
console.log(useranme); // output
```

In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside the function named `hello` and we can't access the variable defined inside a function from outside.

The above code will throw an error `Reference Error username is not defined`.

2. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
{
  const username = 'Arya';
}
console.log(useranme); // output
```
In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside a block("{}") and we can't access the variable defined witn let or const keyword inside a block from outside as it have block scope.

The above code will throw an error `Reference Error username is not defined`.

3. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  let username = 'Arya';
}
console.log(useranme); // output
```
In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside a block("{}") and we can't access the variable defined witn let or const keyword inside a block from outside as it have block scope.

The above code will throw an error `Reference Error username is not defined`.

4. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  var username = 'Arya';
}
console.log(useranme); // output
```
In above code we are looking for the variable named `usename`. The variable is inside a block("{}") and any variable defined witn var keyword inside a block have a global scope and can be accessed from outside as it have block scope.

The above code will not throw any error.

5. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
if (true) {
  var username = 'Arya';
}
console.log(useranme); // output
```
In above code we are looking for the variable named `username`. There is a variable named `username` in the global scope. The variable is which is being declared inside a block("{}") have same name as in global scope and we cannot redeclare any variable declared with let keyword.

The above code will throw an error `Identifier 'username' has already been declared.`

6. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
if (true) {
  let username = 'Arya';
}
console.log(useranme); // output
```
In above code we are looking for the variable named `username`. There is a variable named `username` in the global scope. The variable is which is being declared inside a block("{}") have same name as in global scope but it will not have global scope so both variables will be treated as different variables.

The above code will not throw any error.

7. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
function sayHello() {
  let username = 'Arya';
}
sayHello();
console.log(useranme); // output
```
In above code we are looking for the variable named `username`. There is a variable named `username` in the global scope. The variable is which is being declared inside a fuction have same name as in global scope but it will not have global scope insted it have only functional scope so both variables will be treated as different variables.

The above code will not throw any error.

8. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (var i = 0; i < 10; i++) {
  console.log(i, 'First'); // output
}
console.log(i, 'Second'); // output
```
In above code we are looking for the variable named `i`. There is a variable named `i` in the global scope.

The above code will not throw any error.

9. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (let i = 0; i < 10; i++) {
  console.log(i, 'First'); // output
}
console.log(i, 'Second'); // output
```
In above code we are looking for the variable named `i`. There is no variable named `i` in the global scope. The variable is inside the loop and we can't access the variable defined inside a loop from outside.

The above code will throw an error `Reference Error i is not defined`.
