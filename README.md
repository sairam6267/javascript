# <b>JavaScript</b>

Javascript is browser side script used to make the web pages alive. It is also called as Livescript and works in any browser where it has javascript engine. The beauty of javascript is it can be integrated in HTML and CSS as a script in the browser. The programs in this language are called <i>script</i>.These scrips doesnt require any special compilation to run. Nodejs supports all kind of functions in the javascript.But there are some limitations which we can to in browser side.
<br>
1. JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS functions.

2. JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that’s a safety limitation.

# Fundamentals

## <b>Variables </b>

In javascript variables are declared in different way . Variables are used to store the data. To create the variabels  have key words like let,var,const each key word has specific definition.

<b>1.1 let </b> 

let is used to create variable and this is new way of creating variables in now-a-days
```javascript
//  method 1
let script ;
script  = "javascript";
// method 2 (in single line)
let script = "javascript";
// declare multple variabless in single line
let v1 ="javascript" ,v2 = "is",v3 = "browser Language" ;
```
<b>1.2 var </b> 

var is similar to let , var is old way of declaring the variable but there is slight difference between var and let
```javascript
var script = "javascript";
```
Let see the difference between the let and var keywords

In the below code there is if condition block inside that declared the variable with <b>"let"</b>. In the first method we will get an error [ReferenceError: script is not defined], Hence script varibale is not accessed out side the block. <i>let</i> variables cannot declared twice in the same scope .
```javascript
// method 1
if (true){
    let script =  "javascript";
}
console.log(script) // ReferenceError: script is not defined
//  method 2
if (true){
    let script =  "javascript";
    console.log(script);
}
// method 3
let script = "javascript";
let script = "java"; // SyntaxError: 'script' has already been declared
```
Var is functional scope or global scoped once it declared with <b>"var" </b>keyword.It can be accesed in and out of the block.so these is the key difference between var and let. <i>var</i>, we can redeclare a variable any number of times. If we use var with an already-declared variable, it’s just ignored
```javascript
if (true){
    let script =  "javascript";
    console.log(script)
}
console.log(script)
var script = "javascript";
var script = "java"; 
```
### <b>1.3 const</b>

const variable is used if developer is sure that varibale cannot be changed across the script. so that becomes constant . so new value cannot be reassigned once it is declared.
```javascript
const pi = 3.14;
pi = 3.25; // error, can't reassign the constant!
```

<b>Note:</b> variables declaration can starts with any symbols or characters but should not initialize with digits.
```javascript
let $scripts = "javascript";
let 1scripts = "javascript"; // naming error
```

## <b>Data Types</b>

In javascript every variable value has some type of data. There are 8 data types in the javascript.In this we have primitive and non-primitive data types

## Primitive DataTypes
Primitive datatype is predefined in the java so user cannot be defined it and its store the only one type of datatype in the varibales.

### <b>Strings</b>
String represented in the double quotes or single quotes and backticks.A string length can be empty or non empty it can take any kind of text and stores in the variables.
```javascript
// using double quotes
let dq = "double quotes";
// using single quotes
let sq = 'single quotes';
//----------- there is no difference in single or double quotes format
// using backticks
let bt = `string interpolation with ${sq} backticks`;
console.log(bt);
//---------- back ticks are used to interpolate the variable in the string.
```
### <b>Numbers</b>
There are two types of numbers one is integer and another is the float.
```javascript
let int = 1 ;// integer
let float = 0.25 ;// float
```

### <b>Bigint</b>

In JavaScript, the “number” type cannot safely represent integer values larger than (2^53-1) (that’s 9007199254740991), or less than -(2^53-1) for negatives.As BigInt numbers are rarely needed, we don’t cover them here, but devoted them a separate chapter BigInt. Read it when you need such big numbers.

```javascript
// bigint is created  by the adding n to integer at the last
let bigint = 123455678945612132136124n;
```
### <b>Null</b>

Null value is the special value which defines the varibale with empty value or nothing 
```javascript
let value = null;
```
### <b>Undefined</b>

Undefined(value is not assigned) says that value in is not assigned but variable is declared.
```javasript
let a ;
console.log(a) // "undefined"
```
### <b>Boolean</b>
THe boolean type has two values  true and false. It compare the conditional statements and return true or false values
```javasript
let b = 4;
let c = 5;
let express =  b<c
console.log(express) // true
```

### <b>Symbols </b>


Symbols are immutable and cannot be changed that means is has unique value.Symbols allow us to create “hidden” properties of an object, that no other part of code can accidentally access or overwrite

```javascript
let v1 = symbol("hello");
let v2 = symbol("hello");
// two symbols with the same description

const value1 = Symbol('hello');
const value2 = Symbol('hello');

console.log(v1 === v2); // false
// even though it has same value thye are different .

let user = { // belongs to another code
  name: "John",
  id : 1
};
let id = Symbol("id");
user[id] = "hello";
console.log(user.id); // object id 1 
console.log(user[id]); // symbol id "hello"
```
## Non-primitive Data types

Non-primitive data types are developer definable . It is collection of all primitive data-types.

### <b>Object</b>
 Object can store the different data types and it can mutable.Object has key value pairs. 

 ```javascript
 let obj = {
    num : 1,
    int :2,
    float :3.5,
    [id] : 22,
    string : "hello"
 };

 console.log(obj) //{ num: 1, int: 2, float: 3.5, string: 'hello', [Symbol(id)]: 22 }
 ```

 <b>Note:</b> check the type of data by using the function <i>typeof(variable_name)</i>

 ## <b>Conditions</b>

Sometime we have to perform opertions based on conditons so in that case we have three different clauses being used combined or individual.<b>if,else if,elif</b> and one more specical operator provides by javascript is question mark operatot <b>"?"</b>lets see the difference in code.

<b>Clauses</b>
```javascript
let num = 22;
if (num>22){
    console.log("number is greater than 22");
} else if(num<22 ) {
    console.log("number is less than 22");
} else{
    console.log("number not satisfied");
}
//  number not satisfied
```

logical operators are used if single clause statement has to statisfy multiple conditions.

```javascript
let a =10;
let b = 15;

if (a == 10 && b<20){
    console.log("conditional && operator satisfied");
}
// conditional && operator satisfied
if (a == 10 || b<15){
    console.log("conditional  operator satisfied");
}
// conditional  operator satisfied
```

<b>conditional operator (?)</b>
Conditonal operator same works similar to the clauses but way of writing code is different.it returns the true value.
```javascript
let age =  18;

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';

console.log( message );
// Greetings!
```

if loks like this using clauses
```javascript
if (age < 3) {
  message = 'Hi, baby!';
} else if (age < 18) {
  message = 'Hello!';
} else if (age < 100) {
  message = 'Greetings!';
} else {
  message = 'What an unusual age!';
}
```
 
# <b>Loops </b>

In any programming language loops are used to repeat the same code multiple times . This can happen through iteration process, one execution of the loop is called iteration. loops are very helpful in the case of same process has to do repeatedly.There are different types of loops.

### <b>for loop </b>

for loop is used when number of iterations are defined. It only loops limited times based on range. javascript for loop has four parts.

1. begin              : Executes once upon entering the loop.
2. condition          : Checked before every loop iteration. If false, the loop stops.
3. incrementation     : Executes after the block on each iteration.
4. block              : Runs again and again still the condition is true. 

```javascript
// for loop syntax
for (begin;condition;incrementation){
  // block
}

for (let i =0;i<length("javascript"),i++){
  console.log(i)
}
```

### Skipping the foor loop parts

In for loop we can skip any part , if that part is declared before..

```javascript
let x = 0
for(;x<5;x++){
  console.log(x)
}
let j = 0
// skip incrementation
for(;j<6;){
  console.log(j++)
}
//  create infinite loop by skipping all the parts
for(;;){
  console.log("js")
}
```
### <b> while loop </b>

while loop is used when loop has to run infinite . These loop is important if program has to run long time without break example in program which has scheduler. 

```javascript
while (condition) {
  // block code
}

let i = 0;
while (i < 3) { 
  console.log(i);
  i++;
}
// shows 0, then 1, then 2
```

### <b>do while loop </b>
Do while loop first executes the body and checks the condition . This form of syntax should only be used when you want the body of the loop to execute at least once regardless of the condition being truth

```javascript
let k = 0;
do {
  console.log(k); // first executes the block
  k++;
} while (k < 2);  // check the condition
```

### <b> Break and Continue statements in loops </b>

1. break : Basically loop dont exit until the condition becomes false. so do force exit in the loop we can use break statement inside the block.

```javascript
let f = 0;
while (f < 10) { 
  console.log(f);
  if (f==2){
    console.log("forced the  loop to exit ")
    break; // break statement
  }
  f++;
}
```
2. continue : continue statement is used when we want to skip the iteration if condition becomes false or true, it skips the current loop and executes the next iteration.

```javascript
for(j=0;j<5;j++){
    if(j==3){
        console.log(`"${j} iteration has skipped"`);
        continue;  // continue statement
    }
    console.log(j)
}
```
### <b>switch statement </b>
Switch  is used when if statement has to compare multiple times, switch has multiple case blocks . switch can be replaced by multiple if statement

```javascript
switch (variable_name){ 
  case condition_value: //  case block
    break;
}

// Example
let variable = "javascript";
switch (variable){
  case "javascript":
    console.log(`${variable} matches the case`);
  case String:
    console.log(`${variable} is a string`);
    break;
  case int:
    break;
}
// javascript matches the case
// javascript is a string
```

Rewrite above code in if condition
```javascript
let variable = "javascript";
if (variable === "javascript"){
  console.log(`${variable} matches the case`);
}
if (typeof(variable) === "string"){
  console.log(`${variable} is a string`);
}
if (typeof(variable)=== Number){
 
}
```

# <b>Functions</b>

To achieve the DRY (Dont repeat yourself) we have to use the functions. Functions are written once and called multiple times in the code this is called Dont repeat yourself . In the function we can pass the arguments as parameter which can be used inside the function and return the value. Only local variables can access inside the function outside the function called global variables which can access inside the function.

```javascript
// function declaration
function javascript(arg1,arg2,arg3){ // arguments
  // block of code
}

let global_var = 10;  // can access any where in the script

function add(a1,a2,a3){
  let local_var = 5 ; // can access only inside the script
  add_value = a1+a2+a3+local_var+global_var;
  return add_value
}

let function_val = add(1,2,3)
console.log(function_val)  
```
Another way of writing function is function expression , it means declaring the function using the variable. this type of format only used when
execution reaches it and is usable only from that moment . it can be mostly written inside the function.There is no restriction to use inside the function only it can write oustide the function also

```javascript
// Function Expression
let add = function(a,b){ // function declared to the variable
    return a+b
};
console.log(add(1,2))

function sub(v1,v2){
  let mult = function(m1,m2){ // function expression
    return m1*m2
  };
  return v1-v2+mult(v1,v2)
}

console.log(sub(5,4))
```
Arrow function is another way of declaration of function.It works similar to the function declaration but there is diffrence in the syntax and it for simple single line function evaluates expression on the right side of the function.

```javascript
// single line arroe function
let arrow = (a,b) => a+b ; // expression on the right side
console.log(arrow)
// multiline arrow function
let marrow = (a,b) =>{
  let c = 10;
  let d = 12;
  add = c+d+a+b
  return add
}
console.log(marrow(1,-2))
```
