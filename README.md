# freeCodeCampJsLegacy

As a part of my 100 days of Code challenge, I'm embarking on this journey of learning Javascript Algorithms and Data Structures

I'm also adding a logs file, where I will blog about my progress so far on freecodecamp!

## Basic Javascript

- ### **Strings are immutable**

  once a string is declared we can not reassign one of its characters using index, that is possible only for arrays.

- ### **Function Scope**
  A function can have a local variable with the same name as a Global Variable, within the scope of that function, whenever the variable is called, the overwritten value is used, but coming out of the function, the variable will continue o have the global variable value it had unless and untill reassigned.

When a function does not have a return statement, it processes the inner code but it gives the output "undefined"

- ### **Queue** -

  A queue is an abstract Data Structure where items are kept in order.
  New items can be added at the back of the queue and old items are taken off from the front of the queue.
  new items will be added at the back, old items will be removed from the front, when new item is added, old one at the front will be removed
  _shift(), push()_

- ### **someObject.hasOwnProperty(someProperty)**

- ### **Recursion**

Recursion is like when you ask a question, and part of the answer includes asking the same question again but with a simpler version of the problem. This keeps happening until you reach the simplest form of the problem, which you already know the answer to.

Imagine you have a list of numbers (an array), and you want to multiply the first 'n' numbers together to get a final product. You can do this with a loop, where you start with a product of 1 and keep multiplying it by each number in the array until you reach the 'n'th number.

However, you can also solve this problem using recursion. Here's how:

1. **Base Case**: We need a rule to stop the recursion. In this case, when 'n' becomes 0 or less, we know that there are no more numbers left to multiply, so we return 1 (since multiplying by 1 doesn't change the number).

2. **Recursive Step**: For any 'n' greater than 0, we can find the product of the first 'n' numbers by multiplying the product of the first 'n-1' numbers by the 'n'th number in the array.

So, the recursive function works like this:

- If 'n' is 0 or less, return 1 (base case).
- Otherwise, return the product of multiply(arr, n - 1) \* arr[n - 1], which means the product of the first 'n-1' numbers multiplied by the 'n'th number.

This process keeps repeating, with the function calling itself with a smaller 'n' each time, until it reaches the base case where 'n' is 0 or less. At this point, all the recursive calls finish, and the final product is calculated.

The first valid return statement gets executed first!!

## ES6

- Let, Const
- Arrow Functions
- Default parameters to functions
- Rest parameters - condense a group of elements in to an array [from ES2018, we can apply this to objects also]
- To find maximum value among a group of values - Math.max() expects comma separated arguments but not an array, so it throws an error. Up untill ES5 we needed to use apply()method along with Math.max.apply(null, arr);
- Spread operator is used to unpack an array.
- so now Math.max(...arr) would give us the maximum value of an array.

- Object Short hand property comes in handy to reduce redundancy when we know that the property key and the property value both are same.

- Up until ES5, when we were defining object methods we used the th function keyword, but after ES6, we need not use the function keyword but directly define function

```js
//ES5
const person = {
  name: "Taylor",
  sayHello: function () {
    return `Hello! My name is ${this.name}.`;
  },
};

//ES6
const person = {
  name: "Taylor",
  sayHello() {
    return `Hello! My name is ${this.name}.`;
  },
};
```

##### Constructor Function

A regular function that is used to create objects, which can be used as a blue print if we wanted to create more objects.

```js
// Step 1: Define a Constructor Function
function Person(name, age) {
  this.name = name;
  this.age = age;
  this.sayHello = function () {
    console.log("Hello, my name is " + this.name);
  };
}

// Step 2: Instantiate the Object
var person1 = new Person("Alice", 30);
var person2 = new Person("Bob", 25);

// Using the objects
person1.sayHello(); // Output: Hello, my name is Alice
person2.sayHello(); // Output: Hello, my name is Bob

console.log(person1.name); // Output: Alice
console.log(person2.age); // Output: 25
```

- Untill ES5 we used 'constructor function' and 'new' keyword to create an instance of an object.

- In ES6, **class** keyword was introduced by using the class, we can create objects.
  class keyword declares a new function, to which a constructor is added. This constructor is invoked when new is called to create a new object.

- The constructor method is a special method for creating and initializing an object created with a class.

```js
// Explicit constructor
class SpaceShuttle {
  constructor(targetPlanet) {
    this.targetPlanet = targetPlanet;
  }
  takeOff() {
    console.log("To " + this.targetPlanet + "!");
  }
}

// Implicit constructor
class Rocket {
  launch() {
    console.log("To the moon!");
  }
}

const zeus = new SpaceShuttle("Jupiter");
// prints To Jupiter! in console
zeus.takeOff();

const atlas = new Rocket();
// prints To the moon! in console
atlas.launch();
```

- We can obtain values from an object and also set values of property of an object from inside an object itself using **_getters_**, **_Setters_**

- Getter - returns the value of an object's private variable, without user having to access the variable directly

- Setter - modifies the value of an onject's private variable based on the value passed into setter function.

```js
class Book {
  constructor(author) {
    this._author = author;
  }
  // getter
  get writer() {
    return this._author;
  }
  // setter
  set writer(updatedAuthor) {
    this._author = updatedAuthor;
  }
}
const novel = new Book("anonymous");
console.log(novel.writer);
novel.writer = "newAuthor";
console.log(novel.writer);
```

- A script tag that uses this module type can use the import and export features from ES6.

```html
<script type="module" src="filename.js"></script>
```

```js
const uppercaseString = (string) => {
  return string.toUpperCase();
};

const lowercaseString = (string) => {
  return string.toLowerCase();
};

export { uppercaseString, lowercaseString };
```

- The relative file path (./) and file extension (.js) are required when using import in this way.

```js
import { uppercaseString, lowercaseString } from "./string_functions.js";
```

- To import all the contents of a file into the current file. This can be done with the **import \* as** syntax.

Ex :

```js
import * as myMathModule from "./math_functions.js";
```

Here in the above example, import statement will create an object called myMathModule.

- **export default** syntax is used if only one value is being exported from a file or if we needed to create a fallback value for a file or module.
  We cannot use export default with var, let, or const

```js
//Named
export default function add(x, y) {
  return x + y;
}

//Anonymous
export default function(x, y) {
  return x + y;
}
```
