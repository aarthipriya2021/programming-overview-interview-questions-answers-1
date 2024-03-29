
# OVERVIEW
## Variables
| var | let | const |
| --- | --- | --- |
| global scope | block scope | block scope |
| re-assign and redeclare is acceptable | re-assign and redeclare is not acceptable | re-assign and redeclare is not acceptable |
| value initialization is not compulsory | value initialization is not compulsory | value initialization is compulsory |

## Datatypes

1. Primitive data type
    ```
    String, Number, Boolean, Undefined and Null
    ```

2. Non-primitive (reference) data type
    ```
    Object, Array and RegExp
    ```
    ```
    Arrays :  const cars = ["Saab", "Volvo", "BMW"];
    Objects : const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
    typeof "John"         // Returns "string"
    typeof (3)            // Returns "number"
    ```

## Operators
```JS
JavaScript Arithmetic Operators
```
![image](https://user-images.githubusercontent.com/70185865/147258890-7416e63e-c47e-4c00-98ae-55dc386d04db.png)

```JS
JavaScript Comparison Operators
```
![image](https://user-images.githubusercontent.com/70185865/147259145-55c99bc3-eadf-4795-9acc-83e949817ae9.png)

```JS
JavaScript Bitwise Operators & JavaScript Logical Operators
```
![image](https://user-images.githubusercontent.com/70185865/147259388-ab7bfeb4-10e0-4cb5-acee-08c1b5af0bee.png)

```JS
JavaScript Special Operators
```
![image](https://user-images.githubusercontent.com/70185865/147259489-c576a3bc-adc1-441c-a22e-891d5b0cb5c2.png)

## JavaScript Loops
```JS
for loop
while loop
do-while loop
for-in loop
for-of loop
```
```JS
If counters/indexes are needed while accessing an array or indexes related logical stuff are there it is better to go ahead with for loop.
If there is a need to access properties/keys regardless of the order for-in will help.
If you just need to iterate through data items of an iterable(also if you need to apply some changes maybe) for-of is an obvious choice.
```

## JavaScript break and continue with label
```JS
let i, j;

loop1:
for (i = 0; i < 3; i++) {      //The first for statement is labeled "loop1"
   loop2:
   for (j = 0; j < 3; j++) {   //The second for statement is labeled "loop2"
      if (i === 1 && j === 1) {
         continue loop1;
      }
      console.log('i = ' + i + ', j = ' + j);
   }
}


OUTPUT:
i = 0, j = 0
i = 0, j = 1
i = 0, j = 2
i = 1, j = 0
i = 2, j = 0
i = 2, j = 1
i = 2, j = 2
```

```JS
let i, j;

loop1:
for (i = 0; i < 3; i++) {      //The first for statement is labeled "loop1"
   loop2:
   for (j = 0; j < 3; j++) {   //The second for statement is labeled "loop2"
      if (i === 1 && j === 1) {
         break loop1;
      }
      console.log('i = ' + i + ', j = ' + j);
   }
}

OUTPUT:
i = 0, j = 0
i = 0, j = 1
i = 0, j = 2
i = 1, j = 0
```

## Object
## Array
## String
## Class
## Object
## Exception Handling

# ES6
## var vs let vs const
## DEFAULT PARAMETERS
```JS
function say(message='Hi') {
    console.log(message);
}

say(); // 'Hi'
say(undefined); // 'Hi'
say('Hello'); // 'Hello'
```
## REST PARAMETERS
```JS
ES6 provides new kind of parameter so-called Rest Parameter that has a prefix of 3 dots   ( . . . )

function fnc(a,b,...args) {
  console.log(args)
}
fnc(1,2,3,'A','B','C'); // [3, "A", "B", "C"]
fnc(1,2); // [ ]
```
## SPREAD OPERATOR
```JS
ES6 provides new operator called spread allows to concatenate values

const oddArr = [1,2,3]
const comArr = [ ...oddArr,2,4,6]
console.log(comArr)  //  [1, 2, 3, 2, 4, 6]

```
## Objects Literal
```JS
var sharedType = {
'all': '[none,allUsers,specificGroupOfUsers]',
'none': 'none'
}
sharedType["all"]  // [none,allUsers,specificGroupOfUsers]

```
## DESTRUCTURING
```JS
OBJECT 
------

function getPerson() {
    return null;
}
let {
    firstName,
    lastName
} = getPerson();
console.log(firstName, lastName);
TypeError: Cannot destructure property 'firstName' of 'getPerson(...)' as it is null.
let {
    firstName,
    lastName
} = getPerson() || {};

firstName // undefined
lastName // undefined

==============================================================

const ratings = [
    {user: 'John',score: 3},
    {user: 'Jane',score: 4},
    {user: 'David',score: 5},
    {user: 'Peter',score: 2},
];

let sum = 0;
for (const {score} of ratings) {
    sum += score;
}

console.log(`Total scores: ${sum}`); // 14

--------------------------------------------------------------------------------------------

ARRAY DESTRUCTURING
-------------------

function getItems() {
    return null;
}
let [a = 10, b = 20] = getItems() || [];
console.log(a); // 10
console.log(b); // 20

```
## map function
```JS
const colors = ['red', 'green', 'blue'];
const items = colors.map(function(color){
  return '<li>'+color+'</li>';
});
console.log(items);

O/P:
(3) ["<li>red</li>", "<li>green</li>", "<li>blue</li>"]
0: "<li>red</li>"
1: "<li>green</li>"
2: "<li>blue</li>"
```

## Classes
```JS
class Person {
  constructor(name){
    this.name = name
  }
  walk() {
    console.log(this.name+' is walking');
  }
}

const person = new Person('Vignesh');
const walkFn = person.walk();
console.log(walkFn);

O/P:
VM113:6 Vignesh is walking

```
## Class Inheritance
```JS
class Person {
  constructor(name){
    this.name = name
  }
  walk() {
    console.log(this.name+' is walking !!');
  }
}

class Teacher extends Person{
  constructor(name, degree){
    super(name);
    this.degree = degree;
  }
  teach(){
    console.log(this.name+' is teaching degree '+this.degree);
  }
}

const teacher = new Teacher('Vignesh', 'B.Tech');
console.log(teacher.name);
console.log(teacher.degree);
console.log(teacher.teach());
console.log(teacher.walk());


O/P:
Vignesh
B.Tech
Vignesh is teaching degree B.Tech
Vignesh is walking !!

```
## Modules
```JS

person.js
---------
export class Person {
    constructor(name){
      this.name = name
    }
    walk() {
      console.log(this.name+' is walking !!');
    }
  }
=============================================  
  
teacher.js
-----------
import {Person} from './person';

export class Teacher extends Person{
    constructor(name, degree){
      super(name);
      this.degree = degree;
    }
    teach(){
      console.log(this.name+' is teaching degree '+this.degree);
    }
  }
================================================

index.js
--------

import {Teacher} from './teacher';

const teacher = new Teacher('Vignesh', 'Apple');
console.log(teacher.name);
console.log(teacher.degree);
console.log(teacher.teach());
console.log(teacher.walk());

O/P:
Vignesh
B.Tech
Vignesh is teaching degree B.Tech
Vignesh is walking !!

```
## Named and Default Exports
```JS
Default -> import ... from '';
Named -> import {...} from '';
```
## Arrow function
## Map + Set + WeakMap + WeakSet
```JS
A WeakMap accepts only objects as keys whereas a Map,in addition to objects, accepts primitive datatype such as strings, numbers etc.
```
## TEMPLATE LITERALS/STRINGS:

```JS

Template literals also provides concatenation additionally text with some format.

var a = 123, str = `---
   a is: ${a}
---`;
console.log(str);

O/P:
---
   a is: 123
---

```
## Promises
```JS
let myPromise = new Promise((resolve,reject) => {

let theDecider = true

if(theDecider){ resolve('success') }
else { reject('error') }


}
)


myPromise.then(res => {

console.log('res = ',res)
})
.catch(err => {
console.log('error = ',err)

})
.finally(() => {
    console.log('Experiment completed');
  })


O/P:
res =  success
Experiment completed

```
# ECMAScript 7(2016)
## EXPONENTIATION OPERATOR (**):
```JS
2**5

O/P:
32
```
## INCLUDES(): 
```JS

let arr = ['a','b',2,3,true,false]
arr.includes(true)
true

arr.includes(2)
true

arr.includes('a')
true

```
# ES8 or ECMAScript 2017
## PADSTART
```JS

let str = 'aaa'
console.log(str.padStart(4,'#'))

O/P:
#aaa

```
## PADEND
```JS

let str = 'aaa'
console.log(str.padEnd(4,'#'))

O/P:
aaa#

```
## JavaScript Async Functions
```JS

async function myDisplay() {
  let myPromise = new Promise(function(myResolve, myReject) {
    setTimeout(function() { myResolve("I love You !!"); }, 3000);
  });
  document.getElementById("demo").innerHTML = await myPromise;
}

myDisplay();
```
## Object Entries
```JS

const fruits = {Bananas:300, Oranges:200, Apples:500};

let text = "";
for ( let [fruit, value] of Object.entries( fruits ) ) {
text += fruit + ": " + value + " ";
}

O/P:
'Bananas: 300 Oranges: 200 Apples: 500 '

```
# ES9 or ECMAScript 2018
## ASYNCHRONOUS ITERATION:
```JS

An async iterable object can be used as a loop iteration with the help of for-await-of.

for await ( const str of 'vicky'){
    console.log(' --- '+str);
}
```
## Rest/Spread Properties
https://2ality.com/2016/10/rest-spread-properties.html

# ECMAScript 2021
## string.replaceAll()
```JS

let string = "This is a JavaScript tutorial. JavaScript is used as a front-end & backend for making interactive & dynamic websites.";
console.log(string.replaceAll("JavaScript", "ECMAScript"));

O/P:
This is a ECMAScript tutorial. ECMAScript is used as a front-end & backend for making interactive & dynamic websites.
```
## Logical Assignment operators
### Logical assignment operators with logical AND (&&)
```JS

let a = 10;
let b=4;
a &&= b;
console.log('a='+a)

O/P:
a=4

-------------------

let a;
let b=4;
a &&= b;
console.log('a='+a)

O/P:
a=undefined
```
### Logical assignment operator with logical OR (||)
### Logical assignment operator with Nullish Coalescing Operator (??)
```JS

let a;
let b = 5;
a ??= b;
console.log('a='+a);

O/P:
a=5

-----------------------------
let a=null;
let b = 5;
a ??= b;
console.log('a='+a);

O/P:
a=5
```
## Numeric Separators
```JS

let money = 1_000_000_000_000;
console.log('Money='+money);

O/P:
Money=1000000000000
```
## Private class methods
```JS

class Person {
  constructor(name, age){
    this.name=name;
    this.age=age;
  }
  showName() {
    console.log(`My name is ${this.name}.`)
  }
  // private method
  #showAge() {
    console.log(`My age is ${this.age}.`)
  }
}
const obj1 = new Person("Rohan Kesarwani",22);
obj1.showName()
obj1.showAge()

O/P:
Uncaught TypeError: obj1.showAge is not a function

------------------------------------------------------------

class Person {
  constructor(name, age){
    this.name=name;
    this.age=age;
  }
  showName() {
    console.log(`My name is ${this.name}.`)
    this.#showAge();
  }
  // private method
  #showAge() {
    console.log(`My age is ${this.age}.`)
  }
}
const obj1 = new Person("Rohan Kesarwani",22);
obj1.showName()

O/P:
My name is Rohan Kesarwani.
My age is 22.
```
## Private Getters and Setters:
```JS

Just like private methods, now we can make getters and setters so that they can only be accessed inside a class or by instance created.

class GfG {
  get #Name() {
    return "GeeksforGeeks"
  }
  
  get viewName() {
    return this.#Name
  }
}

let name = new GfG();
console.log(name.viewName);

O/P:
GeeksforGeeks

```
## Promise.any() & Aggregate Error
```JS

It is similar to the Promise.All() method which waits for all promises provided to be resolved before it resolves. Promise.any() method returns a single promise that resolves if any of the promises provided in the iterable (such as an array) has been resolved. If all the promises were rejected, then the promise returned is rejected with a new error known as Aggregate error.

let p1 = new Promise(function(resolve, reject){
  setTimeout(function(){
    reject();
  }, 1000);
});
let p2 = new Promise(function(resolve, reject) {
  setTimeout(function(){
    reject();
  }, 2000);
});
let p3 = new Promise(function(resolve, reject) {
  setTimeout(function(){
    reject();
  }, 3000);
});
try {
  let arr = await Promise.any([
    p1, p2, p3
  ]);
} catch (error) {
// If all promises were rejected, then we will be getting an Aggregate error.
console.log(error);
}

O/P:
AggregateError: All promises were rejected

```




# Interview Questions

## What's the difference between event.stopPropagation and event.preventDefault?
```JS
stopPropagation prevents further propagation of the current event in the capturing and bubbling phases.

preventDefault prevents the default action the browser makes on that event.
```
## What is the use of Void (0)?
```JS
Void(0) is used to prevent the page from refreshing, and parameter “zero” is passed while calling.

Void(0) is used to call another method without refreshing the page.
```
https://www.youtube.com/watch?v=iccdL8-SF7c

## What is the difference between call() and apply() and bind() methods ?

### call method 
```JS
let printFullName = function() {
    console.log(this.firstName+" "+this.lastName)
}

let name = {
    firstName: "Vicky",
    lastName: "Steve"
}

printFullName.call(name);

O/P:
Vicky Steve

---------------------------------------------------------------------

let printFullNameWithStateAndCountry = function(state,country) {
    console.log(this.firstName+" "+this.lastName+" from "+state+" "+country)
}

let name = {
    firstName: "Vicky",
    lastName: "Steve"
}

printFullNameWithStateAndCountry.call(name,'Cupertino', "California");

O/P :
Vicky Steve from Cupertino California
```
### apply method
```JS
let printFullName = function() {
    console.log(this.firstName+" "+this.lastName)
}

let name = {
    firstName: "Vicky",
    lastName: "Steve"
}

printFullName.apply(name);

O/P:
Vicky Steve

----------------------------------------------------------------------

let printFullNameWithStateAndCountry = function(state,country) {
    console.log(this.firstName+" "+this.lastName+" from "+state+" "+country)
}

let name = {
    firstName: "Vicky",
    lastName: "Steve"
}

printFullNameWithStateAndCountry.apply(name,['Cupertino', "California"]);

O/P:
Vicky Steve from Cupertino California
```
### bind method 
```JS
it's just similar to call method but it'll return a copy of function description not action done by that function. So, by storing into another variable a nd call it as function will return the outout of the invoked function.


let printFullNameWithStateAndCountry = function(state,country) {
    console.log(this.firstName+" "+this.lastName+" from "+state+" "+country)
}

let name = {
    firstName: "Vicky",
    lastName: "Steve"
}

let printThis = printFullNameWithStateAndCountry.bind(name,'Cupertino', "California");
printThis()

O/P :
Vicky Steve from Cupertino California
```

## What is the difference between innerHTML & innerText ?
```JS
innerText returns all text contained by an element and all its child elements. innerHtml returns all text, including html tags, that is contained by an element.
```

## What is an event bubbling in JavaScript ?
```JS
Event bubbling is a method of event propagation in the HTML. When an event is triggered in an element inside another element, and both elements have registered a handle to that event. In event bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.
```
## What is Javascript?
```JS
Javascript is a client-side language and the programs or codes written in Javascript run on a browser.  Using Javascript, it is possible to make a web page more intelligent, as it requires the user to provide all mandatory details before submitting the information (filled in HTML elements) to the server. Not only this, using Javascript, we can also restrict a web page to go back to the visited pages; e.g., security measure in net banking services.
```
## Are Attributes and Property the same?
```JS
No. Attributes are something that can give more details on an element like id, type, value etc. Whereas, Property is the value assigned to the property like type="text", value='Name' etc.

* Attributes are additional information which we can put in the HTML to initialize certain DOM properties.

* Properties are formed when the browser parses the HTML and generates the DOM. Each of the elements in the DOM have their own set of properties which are all set by the browser. Some of these properties can have their initial value set by HTML attributes. Whenever a DOM property changes which has influence on the rendered page, the page will be immediately re rendered
```
![image](https://user-images.githubusercontent.com/70185865/148322888-0b9966a9-28c5-45d6-9673-fcfc1ce5760a.png)

## List out the different ways an HTML element can be accessed in a Javascript code.
```JS
(i) getElementById('idname'): Gets an element by its ID name

(ii) getElementsByClass('classname'): Gets all the elements that have the given classname.

(iii) getElementsByTagName('tagname'): Gets all the elements that have the given tag name.

(iv) querySelector(): This function takes css style selector (like #id/.classname/tagname) and returns the first selected element.

(v) querySelectorAll(): Similar to querySelector, this function returns a NodeList of html elements
```
## In how many ways a Javascript code can be involved in an HTML file?
```JS
There are 3 ways to include Javascript in HTML:

External Javascript, load a Javascript file – <script src="FILE.JS"></script>
```
![image](https://user-images.githubusercontent.com/70185865/148480615-9b897f89-890d-413f-af22-2706b11e664c.png)

```JS
Internal Javascript, add a block of code in the HTML document itself – <script>DO SOMETHING</script>
```
![image](https://user-images.githubusercontent.com/70185865/148480720-27d512b4-5863-451d-bf8d-5ebdf461dced.png)
```JS
Inline Javascript, directly add Javascript to an HTML element – <input type="button" value="Test" onclick="FUNCTION()"/>
```
![image](https://user-images.githubusercontent.com/70185865/148480783-3d8cf165-cabd-4ade-ac79-3e9a01e286a8.png)

## Number to String Conversion
```JS
toString: Other data type to String.
val = (5).toString(); converts integer to string.
val = (true).toString(); converts boolean to string.
Convert from Number/Boolean/Date to String.
Number to String: String(9) converts num to string
Boolean to String: String(true) converts bool to str
Date to String: String(new Date()) date to string
Array to String: String([2,2,2]) Array to string.
```
## String to Number Conversion.
```JS
parseInt: String to Int only (no decimals)
val = parseInt('11'); outputs 100 as number
val = parseFloat('22.22') outputs 22.22 as float
Convert from String/Boolean to Number/Date.
String to Number: Number('9') converts str - num
(9).toFixed(4) gives 9.0000 as the output
Boolean to Number: Number(true) converts to no.
Null to Number: Number(null) converts to no. (0)
Chars to Number: Number('ss') give NaN.
```
## What is the difference between Local Storage and Session Storage?
```JS
Local Storage will stay until it is manually cleared through settings or program.

Session Storage will leave when the browser is closed.
```
## What is the difference between null and undefined?
```JS
When used the typeof operator on null; i.e., typeof(null), the value is an object. Whereas, when used the typeof operator on undefined; i.e., typeof(undefined), the value would be undefined.
```
## What are anonymous functions in Javascript?
```JS
an anonymous function is that type of function that has no name

anonymous functions can be used to store a bit of functionality in a variable and pass that piece of functionality around.

Anonymous functions exist only after they are called; whereas, Named functions to exist even if not called.

(function() {  
    console.log('Hello');  
})();  

```
## Explain the term closure.
```JS
The inner functions can be called as closure when it has access to the outer function's variables.
```
## Explain the terms synchronous and asynchronous code.
```JS
The synchronous code is one at a time, or in other words, the synchronous code is blocking. 
And the Asynchronous code is execution is independent of any other actions, in other words, it is non-blocking.
```
## What is the difference between typeof and instanceof operators in Javascript?
```JS
typeof returns a type of entity that it's operated on. instanceof of returns true if an object is created from a given constructor and false otherwise.
```
## What is the difference between textContent and innerText and innerHTML ?
```JS

<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
<script>

function callThis(){
console.log('text-cont - '+document.querySelector('p').textContent); 
console.log('inner-text - '+document.querySelector('p').innerText);
console.log('innerHTML - '+document.querySelector('p').innerHTML);
}
</script>
</head>
<body>
<p>some text and a <span style="visibility: hidden">span tag hidden </span>in it</p>

<h1 onclick="callThis()">This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>


O/P:
text-cont - some text and a span tag hidden in it
inner-text - some text and a in it
innerHTML - some text and a <span style="visibility: hidden">span tag hidden </span>in it
```


























