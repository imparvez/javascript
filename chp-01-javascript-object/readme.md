# Chp 01: JavaScript's Object

Objects are the most common and used data type in Javascript.
Javascript data types:
  - Simple Data Types(Immutable Data Type):
        Number
        String
        Boolean
        Undefined
        Null
    - Complex Data Type:
        Object(Mutable)

What is Object?
A: A list of unordered primitive data types that is stored as a series of name-value pairs.
Each item in the list are called a property.

var sampleObject = {
	firstName: 'Parvez', -> One Item -> propertyName: Value
	lastName: 'Shaikh' -> Another Item -> propertyName: Value
}

Think of object as a list of an items.
Each item is stored by a name-value pair.

propertyName can be string or number.
If number, then it has to be accessed with bracket notation.

var ageGroup = {
	30: "Children", 
	100:"Very Old"
};
console.log(ageGroup.30) // This will throw an error​
​
// This is how you will access the value of the property 30, to get value "Children"​
console.log(ageGroup["30"]); // Children​

Objects can be used to store data or for creating custom methods and functions.
​



