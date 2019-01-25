Things I have learned from : http://javascriptenlightenment.com/JavaScript_Enlightenment.pdf

## Chapter I

- Javascript object have static properties and methods which are functions.
- Javascript constructors are functions that return object instances.
  - An instance is constructed using the new keyword.
  - A constructed object is an instanceof the constructor that was used to construct that object.
- Javascript has native constructors which are built in such as : Object() Number() String() Boolean() Array() Function() Date() RegExp() Error()
  - We can construct objects using these ex. var NUM = new Number(). We call this a complex object.
  - We can also use these to build primitive values var NUM = 2; is a primitive value also built under the hood using its constructor.
  - The former its actually an object, the latter is of type "number".
- We can define our own constructors and build objects with those using the new operator.
- A constructor can be used without the new keyword. In this case it will not create an instance.
- Primitive values are equal by value. 2 === 2.
- Primitive values act like objects when used like objects. In this case they are "wrapped" in an object.
- Primitive values are equal when they are stored in the same locations. Complex values (objects) are not.
  Object values are equal by refrence.
- An instance created from a constructor can have its own independent properties.

## Chapter II
