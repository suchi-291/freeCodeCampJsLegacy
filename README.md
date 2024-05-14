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
*shift(), push()*

- ### **someObject.hasOwnProperty(someProperty)**

- ### **Recursion**

Recursion is like when you ask a question, and part of the answer includes asking the same question again but with a simpler version of the problem. This keeps happening until you reach the simplest form of the problem, which you already know the answer to.

Imagine you have a list of numbers (an array), and you want to multiply the first 'n' numbers together to get a final product. You can do this with a loop, where you start with a product of 1 and keep multiplying it by each number in the array until you reach the 'n'th number.

However, you can also solve this problem using recursion. Here's how:

1. **Base Case**: We need a rule to stop the recursion. In this case, when 'n' becomes 0 or less, we know that there are no more numbers left to multiply, so we return 1 (since multiplying by 1 doesn't change the number).

2. **Recursive Step**: For any 'n' greater than 0, we can find the product of the first 'n' numbers by multiplying the product of the first 'n-1' numbers by the 'n'th number in the array.

So, the recursive function works like this:
- If 'n' is 0 or less, return 1 (base case).
- Otherwise, return the product of multiply(arr, n - 1) * arr[n - 1], which means the product of the first 'n-1' numbers multiplied by the 'n'th number.

This process keeps repeating, with the function calling itself with a smaller 'n' each time, until it reaches the base case where 'n' is 0 or less. At this point, all the recursive calls finish, and the final product is calculated.

The first valid return statement gets executed first!!


## ES6
- Let, Const
- Arrow Functions
- Default parameters to functions
- Rest parameters - condense a group of elements in to an array [from ES2018, we can apply this to objects also]
