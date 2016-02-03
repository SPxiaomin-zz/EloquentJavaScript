# Eloquent JavaScript(second edition)

## Part1

### Chapter6 The Secret Life of Objects

- Methods

    Methods are simply properties that hold function values.
    
    the special variable `this` in its body will point to the object that it was called on.
    
    the method `apply` takes arguments as an array, while the method `call` takes arguments normally.

- Prototypes

    When an object gets a request for a property that it does not have, its prototype will be searched for the property, then the prototype’s prototype, and so on.

    As you might expect, the `Object.getPrototypeOf` function returns the prototype of an object.

    You can use `Object.creat`e to create an object with a specific prototype.

- Constructors

    In JavaScript, calling a function with the `new` keyword in front of it causes it to be treated as a constructor. The constructor will have its `this` variable bound to a fresh object, and unless it explicitly returns another object value, this new object will be returned from the call.
     
    It is a convention to capitalize the names of constructors so that they are easily distinguished from other functions.
     
    Constructors (in fact, all functions) automatically get a property named `prototype`, which by default holds a plain, empty object that derives from `Object.prototype` . Every instance created with this constructor will have this object as its prototype.
    
- Overriding derived properties

    When you add a property to an object, whether it is present in the prototype or not, the property is added to the object itself, which will henceforth have it as its own property. If there is a property by the same name in the prototype, this property will no longer affect the object. The prototype itself is not changed.

- Prototype interference

    We can iterate over all properties values in the object using a for/in loop and test whether a property is in there using the regular in operator. But unfortunately, the object’s prototype gets in the way.
    
    JavaScript distinguishes between `enumerableand` `nonenumerable` properties.All properties that we create by simply assigning to them are enumerable. The standard properties in Object.prototype are all nonenumerable, which is why they do not show up in such a for/in loop.
    
    It is possible to define our own `nonenumerable` properties by using the `Object.defineProperty` function, which allows us to control the type of property we are creating.
    
    we can use the object’s `hasOwnProperty` method. This method tells us whether the object itself has the property, without looking at its prototypes.

- Prototype-less objects

    `Object.create` function, which allows us to create an object with a specific prototype. You are allowed to pass `null` as the prototype to create a fresh object with no prototype. 

- Polymorphism

    When a piece of code is written to work with objects that have a certain interface—in this case, a toStringmethod—any kind of object that happens to support this interface can be plugged into the code, and it will just work.
    
