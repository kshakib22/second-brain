Objects inherit properties and methods from a prototype **object**. This is different from traditional OOP where inheritance is done through **class** definition. Check [OOP in JavaScript](OOP%20in%20JavaScript.md) for detailed usage of this paradigm.

- You can create objects **without** any class definition using `{}`, similar to a dictionary in Python.
- There is no separate constructors involved
- There is no class keyword, constructors are essentially functions



Each object has a hidden link to a prototype object from which it inherits.

```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log("Hello, my name is", this.name);
};

const person1 = new Person("Alice", 30);
const person2 = new Person("Bob", 25);

person1.greet(); // Output: Hello, my name is Alice
person2.greet(); // Output: Hello, my name is Bob

console.log(person1.hasOwnProperty('greet')); // false (inherited from prototype)
console.log(Person.prototype.hasOwnProperty('greet')); // true (defined on prototype)

```