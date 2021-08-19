# Basic Concepts to understand when working with Obj-C


## Atomic vs. nonatomic [Extra can be found here](https://medium.com/@YogevSitton/atomic-vs-non-atomic-properties-crash-course-d11c23f4366c)

### Atomic 
Defining a property as atomic will guarantee that a valid value is returned, it doesn't mean that it will be your expected value. Atomic values are not thread safe. If you have mutliple thread that update or read an atomic value it's value will be returned but you don't know if it's a stale value or not. 

Atomic is the default value for new properties.

### nonatomic
Defining a property as nonatomic does not gurantee a valid value will be returned. It could be the correct value, parially written to value, or even a garbage value. nonatomic values are ***not thread safe***. Marking a value as non atomic does come with enhacned speed. 

## Readonly

## Copy 
