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
