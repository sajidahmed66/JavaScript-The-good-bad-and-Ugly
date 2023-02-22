### JavaScript the Good bad & Ugly

If we offend,it is our good will
That you should not think, we come not to offend,
But with good will. To show our simple skill,
That is the true beginning of our end.
—William Shakespeare, A Midsummer Night’s Dream;

Scope: 
    the purpose is to learn javaScript and this repo will contain my studies and notes. i do not indend to have this as guide for others for now but might redesign it later to a reading material/guides. 
    
big words:

    -syntax parser
    -execution context
    -lexical environments
    -single threaded & syncronous
    -Invocation
    -Variable Environment
    -Dymanic Typing
    -Peimitive type
    -Operator
    -Operator Precedence
    -Operator Associativity
    -Coercion
    -NameSpace
    -Expression
    -Mutate/Immutable
1. Syntax parser: A program that reads my code and determines what it does and checks if the grammar is valid.(My code is not magic someone wrote a program to translate it for the computer)

2. Lexical Environment: Where something sits phyicially in the code that I write. 
   
    "Lexical" meanes 'having to do with words or grammer'. a lexical environment exists in a programming laguages in which "where you write something is important" 

3. Exicution context : A Wrapper to help manage the code that is running. Threr are a lot of lexical environments. Which one is currently running is managed via execution context. it can contain things beyond what i've written in my code. 

4. Single Threaded & syncronous : One command at a time and in order...

5. Invocation: Running a function(in js , by using paranthesis after functions name)

6. variable environment: Where the variables live (and how they relate to each other in memory)

7. Dynamic Typing: I don't tell the engine what type of data the variable holds. it figures out while the code is while the code is running.(The variable can hold different types of values because it is figured out during the execution.)  

8. Primitive type: A type of data that represents a single value.(that is not an object or an array.)

   Primitive types:
        -undefined: represents lack of existence.(never set a variable to undefined).
        -null: also represents lack of existance.(can set a variable to null).
        -boolean: true or false.
        -number: Floating point number (there is always some   decimals). Unlike other programming language, In javaScript there is only one 'number' type... and it can make math weird
        -string: a sequrnce of characters: Both '' and "" can be used.
        -symble: used in javascript version ES6.(details later explored). 
9. Operator: A special type of function that is syntatically written diffrently.( Generally, operator receives of takes two parameter and returns one result.) (Explaned in my words).

10. Operator Precedence: Which oparator function gets called First.(functios are called in order of precedence,Higher precedence wins or called first)

11. Operator Associativity: what order Operator function gets called in first; left-to-right or right-to-left.(When function has same precedence).
        the left-to-right means that left one gets exicuted first then right one, and right-to-left is vice-versa.

12. Coercion: Converting an Value from one type to another.(this happens quite a bit as js is loosly typed)

13. Namespace: A container for Variables and Functions. Typically to keep Variables abd functions with the same name separate.

14. First Class Function : Everything that can be done with other types(as in number , boolien objects etc) can be done with FUNCTIONS. (Assign them to variables, pass them around and create them on the fly)

15.Expression: A unit/line of code that results in a value. it does not have to save to a variable. for example 2===3 is an expression that reselts in a value in this case is false;

16.Mutate: To change something. "Immutable" means to change some thing.


## The creation phase and the execution phase:

At first the javascript engine reads the full code and creates Memory contexts(location) for Variables and Functions. In the memory the function stays as whole and variables without a value(undefined). the value of the variable gets assigned later in  the execution phase.
this creation of memory for variable and functions are called the creation phase.



## The function Invocation and the execution Strack:

In js function is executed only when it is invoked(called with parenthesis ()) and when it is called a new execution context is created and is placed on the execution stack.

## How the oparetor and what the oparetor" 
    oparetor is simply a function that takes two parameter and returns a single value. 
        3+4   //returns 7. the oparetor + takes two param. 
    In other type language(lisp/commonlisp) of this type of syntax is common
        +(3,4); // here the function "+" takes two param 3 and 4 seperated by comma. this way of placeing "+" before the params is call prefix notation.
    What javaScript uses is infix notation, meaning the oprator goes in between two parameter like 3+4; minus the comma and parenthesis, Which is more human readable.
    
    reference is in mozila developer guide.
    
    i need to write an example to explane operator precedence and associativity(mendokse...)
    
    
## Coercion

Because javaScript is loosely typed Coercion is done by JS engine under the hood


for a common example let's try the following code:
    
    var a = 1 + 2 
    console.log(a)

the output will be 3 but 

     var a = 1 + "2" 
     console.log(a)

the output will be 12 as javascript will convert type of 1 to '1' and contatinate two strings thus giving the value of '12' with type string.




## framework aside: 

## Object and The Dot: 
 []--> computed member access oparetor for object.
 an object can have a property(primitive type),nested odject , and method(function) 
 
## Object Literal 
another way to create an object is use of literal, like this 

    var person ={ firstName: 'Mojid", lastName: 'Mia' }
    
this is same as new Object() but much faster and more readable to humans.

#### JSON vs JsObject:
-JSON or javascript object notation is inspired by javaScript Object literals.
    
    -diffrence is that in json the properties are always wrapperd in quotation.
    -JSON is a subset of JavaScript object.

 
## Functions are Objects:
 
 in javascript functions are objects. and All Functions in javaScript is treated as First Class Functions.
 
 Just like any object, Function object resides in memory.Though,it's a special type of object because it has all the properties of an object but has some other special properties: 
 
 Name- though it can be anonymous and not have a name.
 
 Code property - where the actual lines of code resides.
 
The code that you write gets placed in a special property of the function object. So it isn't the code you write is a function rather the function is an object with other properties . and the code that is written is one of those properties that beed added on to it. What special about the code property is that it is invocable. You can say run that code and that's when the execution context creation and execution happends.

It is important that you have this mental model of function in your mind. You have to think of function as objects whose code is just happened to be just one the properties. There are other things that functions can have attached to it. And it can be moved around and copied just like other object.

## Function Expression and Function statement:
 
 this is a function statement.
 
 function greet (){
 console.log("hi")
 }
 
 this a a function expression 
 
 let greet = function (){
 console.log("hi")
 
 }
 
 
 the function statement get called during creation phase and gets hoisted but expression gets call and crated during exicution phase. 
 
 
 
## By value and by reference:
-Primitive values get copied by passing, referrencing or setting equal to another , a new memory referrence is being created. this is called  "By value"

-But in case of object values do not get a new location in memory but they point to same reference/memory location. So object types passes the referrence only. this is called "By reference". 