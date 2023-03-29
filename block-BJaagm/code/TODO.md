1. What does thread of execution means in JavaScript?
 A thread of execution refers to the sequence of instructions that are executed one by one by the JavaScript engine. JavaScript is a single-threaded language, which means that only one thread of execution can run at a time.

The JavaScript engine reads the code line by line, and for each line, it executes the appropriate instructions. If the instruction involves fetching data from a server or performing a time-consuming operation, the thread of execution may have to wait until that operation is complete before moving on to the next line of code.

It's important to note that JavaScript also supports asynchronous programming through mechanisms such as callbacks, promises, and async/await. These mechanisms allow the thread of execution to continue running while certain operations (such as network requests) are being performed in the background. This helps to prevent the user interface from becoming unresponsive and improves the overall performance of JavaScript applications.

2. Where the JavaScript code gets executed?
In Global Execution Context.

3. What does context means in Global Execution Context?
The context of the Global Execution Context refers to the state of the program at a given moment in time. It includes information about the current value of all the variables in the program, the current execution point in the program, and the current scope chain.
The context of the Global Execution Context is important because it determines how the JavaScript program behaves. For example, when a function is called, a new Execution Context is created, and this context inherits the context of the parent function. The context of the Execution Context determines how the function is executed, and what variables and functions are available within the function.

4. When do you create a global execution context.
 the Global Execution Context (GEC) is the initial context that is created when a JavaScript program starts running. The Global Execution Context represents the environment in which the global JavaScript code is executed.


5. Execution context consists of what all things?
 It includes all the variables and functions that are available globally in the JavaScript program.

6. What are the different types of execution context?
In JavaScript, there are three different types of execution contexts, which are:

Global Execution Context: The Global Execution Context is created when the JavaScript program starts running. It represents the environment in which the global JavaScript code is executed. All the code that is not inside a function is executed in the Global Execution Context.

Function Execution Context: The Function Execution Context is created whenever a function is called. It represents the environment in which the code inside the function is executed. Each time a function is called, a new Function Execution Context is created, which has its own variables, scope, and this keyword.

Eval Execution Context: The Eval Execution Context is created when code is executed using the eval() function. It represents the environment in which the code passed to the eval() function is executed. The variables and functions created inside the Eval Execution Context are not visible outside the context.

7. When global and function execution context gets created?
Global Execution Context: The Global Execution Context is created when the JavaScript program starts running. It represents the environment in which the global JavaScript code is executed. All the code that is not inside a function is executed in the Global Execution Context.

Function Execution Context: The Function Execution Context is created whenever a function is called. It represents the environment in which the code inside the function is executed. Each time a function is called, a new Function Execution Context is created, which has its own variables, scope, and this keyword.

8. Function execution gets created during function execution or while declaring a function.
The Function Execution Context is created whenever a function is called.

9. Create a execution context diagram of the following code on your notebook. Take a screenshot/photo and store it in the folder named `img`. Use `![](./img/image-name.png)` to display it here.



```js
var user = "Arya";

function sayHello(){
  return `Hello ${user}`;
}

var userMsg = sayHello(user);
```

<!-- Put your image here -->

![](./img/image-name.jpg)



```js
var marks = 400;
var total = 500;

function getPercentage(amount, totalAmount){
  return (amount * 100) / totalAmount;
}

var percentageMarks = getPercentage(marks, total);
var percentageProfit = getPercentage(400, 200);
```

<!-- Put your image here -->

![](./img/image-name.jpg)



```js
var age = 21;

function customeMessage(userAge){
  if(userAge > 18){
    return `You are an adult`;
  }else {
    return `You are a kid`;
  }
}

var whoAmI = customeMessage(age);
var whoAmIAgain = customeMessage(12);
```

<!-- Put your image here -->

![](./img/image-name.jpg)