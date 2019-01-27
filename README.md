_Sometimes we rush to learn the new ES6 features without knowing where we all started. Here is a book from years ago and in short what I managed to learn and solidify from it. I am aware that some of the things here may be deprecated, in that case we will learn why we got rid of them._
_I like to write what I have learned because it is scientifically proven that it enforces your knowledge, I suggest you try it too._
_Feel free to open pull requests if you have suggestions and/or corrections._

## Chapter I

- Javascript objects have static properties and methods which are functions.
- Javascript constructors are functions that return object instances.
  - An instance is constructed using the new keyword.
  - A constructed object is an `instanceof` the constructor that was used to construct that object.
- Javascript has native constructors which are built in such as :
  ```javascript
    Object() Number() String() Boolean() Array() Function() Date() RegExp() Error()
  ```
  - We can construct objects using these ex. `var NUM = new Number();`. We call this a complex object.
  - We can also use these to build primitive values `var NUM = 2;` is a primitive value also built under the hood using its constructor.
  - The former its actually an object, the latter is of type "number".
- We can define our own constructors and build objects with those using the new operator.
- A constructor can be used without the new keyword. In this case it will not create an instance.
- Primitive values act like objects when used like objects. In this case they are "wrapped" in an object.
- Primitive values are equal when they are stored in the same location. Complex values (objects) are not.
  Object values are equal by reference.
- An instance created from a constructor can have its own independent properties.

## Chapter II

- Objects can contain most of the javascript values and may be nested.
- Object properties can be changed using dot or bracket notation.
- An object property can be deleted using the `delete` keyword. It cannot be deleted by setting it to undefined.
- If a property is not found on the object javascript looks up the prototype chain, if it does not find it there it returns undefined.
  - We can check if a property pertains to an object using hasOwnProperty(It does not check the prototype chain).
  - We can also use `in` . This checks the prototype chain.
- Object properties can be iterated using a for in loop. It iterates over the values that are iterable.
- Besides the native objects there are also host objects. These can be found on the host environment such as the browser.

## Chapter III

- All objects inherit from Object.prototype
- Example: If we add a property to Object.prototype we will be able to find that on a String

  ```javascript
  Object.prototype.foo = "foo";

  var myString = "bar";

  console.log(myString.foo); // logs 'foo', being found at Object.prototype.foo via prototype chain
  ```

  - By changing Object.prototype you can build a new version of javascript. Therefore this is not a good practice. Unless you want to confuse people. Then it is very advisable.

## Chapter IV

- Function instances have this properties arguments, constructor, length and these instance methods apply(), call(), toString()
  - Functions are passed `this` and `arguments` as parameters, this book is based on an older version of javascript but we can see that these parameters are not passed in ES6 arrow functions.
- Functions always return a value, default is undefined.

## Chapter V

- The scope in Javascript works similar to the prototype chain, but these are two different things. Similar in the sense that what is defined in the containing object can be accessed to the functions. However you cannot access the variables defined in other functions that have no relations in the scope chain.

## Chapter VI

- All variables except this and arguments follow lexical scope.
- `this` inside two or more nested functions will refer to the global object.

  ```javascript
  var myObject = {
    func1: function() {
      console.log(this); // logs myObject
      var func2 = (function() {
        console.log(this); // logs window, and will do so from this point on
        var func3 = (function() {
          console.log(this); // logs window, as it’s the head object
        })();
      })();
    }
  };
  myObject.func1();
  ```

  - **This was fixed later by either using the bind() method or arrow functions who retain the this value of the enclosing lexical context.**

## Chapter VII

- The scope chain, if you think about it, is not that different from the prototype chain. Both are simply a way for a value to be looked up by checking a systematic and hierarchical set of locations.
- **The scope chain is also known as the lexical scope.**
- Variables defined in functions are available in that function not outside. If they don't find a variable which is invoked they will look outside of the scope to find it. The last place they will look in is the global object.

_Bonus : This book uses the word Grok which means : Understand (something) intuitively or by empathy._
