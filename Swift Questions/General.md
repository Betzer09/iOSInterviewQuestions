# A general set of swift releated questions

## Lazy vs eager loading

Lazy(AKA deffered loading): is what it sounds like. It means an image, expensive opertions, don't happen unless the image or operation is required. 
Eager loading: - is the concept of force-loading. 

## Strong, Weak, Unowned
The term stems from (ARC: Automatic Reference Counting) and is used by swift to decide whether or not something should be removed from memory. Think of it using an imaginary counter to decide whether or not an object should be in memory. Strong reference cannot be nil. 

### Strong: 
Increments the reference count by 1 an ensures that an object cannot be deallocated. It's often safe to use a strong reference when a hierachy relationships of objects are linear meaning it's flows from parent to child. 

### Weak: 
Does not increase or decrease an objects reference. Weak references can be nil. 

### Unowned: 
Acts a lot like week and does not increase or decrease an objects reference count but **unowned references can be optional**


## What is a retain cycle 
Imagine a circle with a list of arrows all pointing the same direction. In code this is bad thing. If you think back to Strong & Weak types you will remember that swift used a counter to decide if something should be in memory or not. If all the arrows are point at each other the reference count can never go to zero, which impacts performace and can create unintended behaviors. 

## Optionals - (Some vs None) & Associated values
Are allow you to define a property that has not yet been set, often allowing to set the value under the hood. 

For example an optional could be written something like this using an enum & associated values. 

```
enum Optional<Wrapped> {
    case some(Wrapped)
    case none
}
```
[A great artical on this can be found here](https://khanlou.com/2018/04/enums-and-optionals/)

### Associated Values 
Associated values allows you to store different tipes of data types under one object. For example 

```
enum Barcode {
    case upc(Int, Int, Int, Int)
    case qrCode(String)
}
```

This allows you to define how `Barcode` is stored vs having to worry about the implementation. 