**Everything** in JavaScript is essentially an object, even primitive data types like *numbers* and *strings*. Objects are collections of *key-value pairs* where the key acts like a label and the value is the data associated with that key. 

#### Creating simple objects

Simple objects can be created without needing a constructor. You can create objects using curly braces `{}`  and `:` . The `:` is used to separate the name of property/method (key) from its values. Check out [[JSON]], [Naming conventions](Naming%20conventions.md). 

```js
// creating a person object without class definition/constructor
// uses {} and :
const person = {
  name: "Alice",
  age: 30,
  greet: function() {
    console.log("Hello, my name is", this.name);
  }
};
```

#### Classless Constructors 

OOP in Javascript is weird because it is actually [Prototype based](Prototype%20based.md) instead of traditional object oriented principles. The constructor (if any) is just a function. There is no concept of 'class' definition or constructor methods. The constructor typically define the properties and methods that will be shared by all objects created using that constructor.

Below is an example of creating a simple constructor in JS. Inside the constructor, `this` refers to the new object being created. Compared to creating object *without* constructor, this uses `=` sign.

```js
function Person(name, age) {
  this.name = name;
  this.age = age;
  this.greet = function() {
    console.log("Hello, my name is", this.name);
  };
}

const person1 = new Person("Bob", 25);
const person2 = new Person("Charlie", 40);

person1.greet(); // Output: Hello, my name is Bob
person2.greet(); // Output: Hello, my name is Charlie
```

Notice how the method is also treated as a 'variable' called greet setting it equal to a function.

#### Dynamic addition of properties/methods

In JS, both properties (using dot operator) ***and*** methods (using function) can be added after an object has been instantiated. However, this should be done in moderation to prevent confusion.

```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}

const person1 = new Person("Alice", 30);
person1.occupation = "Software Engineer"; // Adding a new property "occupation"

// adding a new method
person1.greet = function() {
  console.log("Hello, my name is", this.name);
};

person1.greet(); // Output: Hello, my name is Alice

```
