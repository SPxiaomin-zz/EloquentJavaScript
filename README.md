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
