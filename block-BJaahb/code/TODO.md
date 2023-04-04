Create the execution context diagram for the following code snippets:

```js
function outer() {
  let b = 10;
  function inner() {
    let a = 20;
    console.log(a + b);
  }
  return inner;
}
let getSum = outer();
let num = getSum();
```

2.

Create the execution context diagram for following code. Also write the output of the code below.

```js
function getCounter() {
  let count = 0;

  return () => {
    return count++;
  };
}

let counter = getCounter();

counter(); // output 1
counter(); // output 2 
counter(); // output 3
counter(); // output 4
```

3. Create the execution context diagram

```js
function makeColorChanger(color) {
  return function () {
    document.body.style.backgroundColor = color;
  };
}

let blue = makeColorChanger('blue');
let tomato = makeColorChanger('tomato'); 

blue();
tomato();

// What will be the background color after the execution of last line : Tomato
```
![alt text](./img/WhatsApp%20Image%202023-04-04%20at%2010.18.04%20AM.jpeg)
![alt text](./img/WhatsApp%20Image%202023-04-04%20at%2010.34.04%20AM.jpeg)
![alt text](./img/WhatsApp%20Image%202023-04-04%20at%2012.19.29%20PM.jpeg)

