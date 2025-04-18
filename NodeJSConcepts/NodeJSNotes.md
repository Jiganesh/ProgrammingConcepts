Any Application that can be written in Javascript will eventuall be written in Javascript.
    - Jeff Atwood 2007 Founder, stackoverflow

Everything that runs Javascript, has Javascript Engine.




What is NodeJS ?
Node.js is a cross-platform, open-source JavaScript runtime environment that can run on Windows, Linux, Unix, macOS, and more. Node.js runs on the V8 JavaScript engine, and executes JavaScript code outside a web browser.


Who created NodeJS ?
In 2009 NodeJS was born and Ryan Dahl building project out of curiosity, Node JS uses V8 engine. Joyent offered to fund nodejs and ryan dahl started working for them. He named nodeJS as WebJS initially because he wanted to build web server.

Apache server was a blocking server and Ryan wanted to create non blocking I/O. In 2010 npm happened which is package manager for node. node is popular because of npm. When node was built it was built for macos and linux but 2011 joyent and ms provided support for node in windows. Isaac (founder of npm) was then leading nodejs after ryan left company. In 2014 guy name fedor created io.js . in 2015 there was nodejs foundation. In 2019 JS foundation + node JS foundation was merged = Open JS foundation . Open JS took ownership and they maintain the node JS now.



What is NodeJS - JS on Server

What is Server ?

When JS was used on browser was done by frontend but use python and java in backend but with NodeJS you can work with JS in backend




How is NodeJS has C++ code ?
JS Engine V8 is written in C++ program - check v8 github and 72% code in written in JS


What is V8 Engine ?
Go to V8 Website


NodeJs is a C++ application with v8 embedded into it, when v8 can execute JS why we need JS


V8 follows ECMAScript standard (which is followed by JS, Jscript and Actionscript )


NodeJS adds superpowers to V8 and API and this is known as JS Runtime.


Go to node js repository -> 



TC39 is committy of 39 people who manages this standards fo ECMA Script


Install NodeJs in Computer

```bash
# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash

# in lieu of restarting the shell
\. "$HOME/.nvm/nvm.sh"

# Download and install Node.js:
nvm install 20

# Verify the Node.js version:
node -v # Should print "v20.19.0".

nvm current # Should print "v20.19.0".

# Verify npm version:
npm -v # Should print "10.8.2".

```


npm is automatically installed with nodejs



What is Node REPL ?
REPL is Read Evaluate Print Loop, with node command on terminal you will go into NODE REPL

.exit to exit node REPL




```js


// app.js 

var name = "Namaste NodeJS"


var a = 10;
var b = 20;



```

To executed the file

> node app.js



The global object inside node js


```js
console.log(global)

```

global is one of the superpowers given by node js 

```js
console.log(this) // Empty Object

```


IN the browser window , this , self (webworker), frames were referring to same global object


to standardize this OpenJs came with proposition to use globalThis which is global across all Javascript runtime.


console.log(globalThis);


```js

console.log(globalThis === global) // true
```


Now app.js and xzy.js are two modules - How will you get code in xyz module in app.js ?






```js


require ("./xyz.js"); // require function is always available , another superpower from nodeJS


```



```
sum.js


function calculateSum (a, b) {

    console.log(a+b)
    return a + b

}





```




```
app.js


require("/sum.js");


var a = 10
var b = 30


calculateSum(a+b) // calculateSum is not defined 


```

By Default modules are protected and modules protectstheir variable and functions from leaking




```
sum.js


function calculateSum (a, b) {

    console.log(a+b)
    return a + b

}


module.exports = {
    x : x
    calculateSum : calculateSum
}

can also be written as


module.exports = {
    x , calculateSum 
}


```


```js

app.js


const obj = require ("./sum.js");


var name = "Namaste NodeJS";

var a = 10;
var b = 20;


obj = calculateSum(a, b);
console.log(obj.x);

```


OR


```js

app.js


const {x, calculateSum} = require ("./sum.js");


var name = "Namaste NodeJS";

var a = 10;
var b = 20;


calculateSum(a, b);
console.log(x)

```



Also 


require("./sum") will work it is assumed you are using .js





CommonJS modules cjs
ES modules mjs



CJS 

- 

module.exports
require()


by default used in NodeJs

older way of doing things

SYnchronous way

non strict mode









MJS

-

import

export


by default used in React Angular



has Asynchronous Optional

strict mode



package.json



```
{
    "type":"module"
}


```




```
sum.js


export var x = 10;

export function calculateSum (a, b){
    return a + b
}


```
```

import {x, calculateSum} from "./sum.js"




```


What is strict mode and non strict mode ?






What is module.exports ? 


```
console.log(module.exports) // Empty Object = {}

module.exports.x = x ;
module.exports.calculateSum = calculateSum;


```









Nested Modules 


Calculate Folder
- multiply.js
- sum.js




fuction caculateMultiply(a, b){
    const result = a * b ;
    return result
}

module.exports = {calculateMultiply}



calculate

const {calculateMultiply} = require("./calculate/multiply.js")


const {calculateSum} = require ("./sum)





What if you had json file ?  How to you import from json file

require("./data.json")



```

{
    "name":"jiganesh"
    "age" : 23
}
```


require("node:util")





Diving into the node js github repository


Creating a module works the same way as functions and constent in module is wrapped inside the function and that is why you cannot access 




ALl the code of the modoule is wrapped inside a funntion (IIFE) - Immediately Invoke function expression



(function () {

    All the code of module is inside this function
    
})()



What is IIFE ? 



Keeps functions and modules safe !





How are variables and functions private in different modules ? The answer is IIFE (wrapping code) and require statement



How do you get access to module.exports ?

Nodejs passes modules as a parameter to the IIFE. 

```


function(module.exports={}, require){

    require



}



```



5 Step mechanism of require to get module and executed


- Resolving the module - local path or json path or node:module
- Loading the module - file context is loaded according to file type
- wraps inside IIFE (compile)
- Evaluation module.export
- caching




All the node js code is wrapped inside IIFE and then passing the function the giving it to v8


NodeJS repository ?



NodeJS github repository - opensource project


deps folder - dependencies has v8 folder

libuv is the beast - nodejs is popular because of libuv


Go read NodeJs documentation 





# Libuv and async IO


Node.js has an event-driven architecture capable of asynchronous I/O



Javascript is synchronous single threaded language.



Example : You are running a restaurant coke, pizza , noodles in menu, 


take 5 min for noddles
take 10 min for pizza
take 0 min for coke


Synchronous

Person A order Coke - 0sec
Person B order noddles - 5min
Person C order pizza - 10min
Person D order Coke - 0 sec - he got order after 15 min
Person E order noddles - 5 min - he got order after 20 min



Asynchronous

Person A order Coke - 0sec
Person B order noddles - 5min - gives order and waits in waiting area
Person C order pizza - 10 min - gives order and waits in waiting area
Person D order Coke - 0 sec - he got order after 0 min
Person E order noddles - 10 mingives order and waits in waiting area



libuv is a multiplatform  support library with a focus on Asynchronous I/O written in C.

NodeJs is asynchronous due to libuv


sync , async, setTimeoutZero 


```







```
