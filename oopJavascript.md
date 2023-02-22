# ::Object Oriented JavaScript::

 1. Every thing is an object in javascript except primitive types 
 2. The types can behave like an object. JavaScript wraps the primitive types in an object for it to behave like an object.
 
 ## topics studing:
 -Oject literal notation.
 -Javascript classes and notation.
 -Mehod chaining.
 -Iheritence.
 -Prototype & Prototype inheritence.
 
 ### Object Letreal Notation:
 Can initiate an object with a literal which is a curly braces {}.
 
 An object can have property and method. let example: 
 
    var person ={
        name: "Mojid",
        age: 24,
        sayHello(){
        console.log(`${this.name} says hello!`)
        }
    };
    
For person is an object, name & age are property and sayHello is a method(aka function.)

getting a property value or invoking a method 
    person.name, person.age, person.sayHello,
    
we can also use computed member access oparetor -->[] to get a poperty 
le example :

    person[name]


To update a property do a assignment oprator with the object.property and value.

    person.name = "sajid" // new value becomes sajid
    
to dinamically access a property, a variable assigned to a property name can be used with "computed member access oparetor --> []";

    var prop = name;
    person[prop] // == person.name 
    
### JavaScript Classes and Notation:

 JavaScript do not have built-In "Classes" instade it has "Prototype".
 In ES6 Classes that were introduced was nothing but a Syntactic sugar that uses JavaScript Prototype. 
 
 These "class" Syntax is easy to use as it looks familiar to object_oriented_programming Paradime.
 
 le example:
 
    class User {  //by convention Capitalize the name of the class
        constructor(email, name){
        //initiation the new object to have some property.
            this.email= email;
            this.name = name;
        }
    
    }
    
    var userOne = new User('mojid@momo.com', Mojid); // new keyword creates a new object from User class
    console.log(userOne)// {email: 'mojid@mom.com', name: 'Mojid'}
    
    var userTwo = new User('sajid@momo.com', Sajid); 
    
Adding method to the class:

    
     class User {  //by convention Capitalize the name of the class
        constructor(email, name){
        //initiation the new object to have some property.
            this.email= email;
            this.name = name;
            this.score = 0;
        }
        // add a login method
        logIn(){
            console.log(`${this.email} is now logging in`)
        }
        loOut(){
            console.log(`${this.email} is now logging out`)
        }
        updateScore(){
            this.score++;
            console.log(ths.email , 'score is now', this.score);
        }
    }
    
    // calling a method 
    var userOne = new User('mojid@momo.com', Mojid);
    userOne.logIn() // log -->
    

### Method Chaining::


### Inheritance:: 


 