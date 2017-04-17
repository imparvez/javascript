# Chp 01: JavaScript's Object

Objects are the most common and used data type in Javascript.
Javascript data types:
  * Simple Data Types(Immutable Data Type)
  	* Number
  	* String
  	* Boolean
  	* Undefined
  	* Null
  * Complex Data Type
  	* Object(Mutable)

### What is Object?
**A:** A list of unordered primitive data types that is stored as a series of name-value pairs.
Each item in the list are called a property.

```js
var sampleObject = {
	firstName: 'Parvez', // -> One Item -> propertyName: Value
	lastName: 'Shaikh' // -> Another Item -> propertyName: Value
}
```

Think of object as a list of an items.

Each item is stored by a name-value pair.

propertyName can be string or number.

If number, then it has to be accessed with bracket notation.

```js
var ageGroup = {
	30: "Children", 
	100:"Very Old"
};
console.log(ageGroup.30) // This will throw an error​
​
// This is how you will access the value of the property 30, to get value "Children"​
console.log(ageGroup["30"]); // Children​
```

Objects can be used to store data or for creating custom methods and functions.
​

### Creating Objects:

There are two ways to do it

1. Object Literals(A JavaScript object literal is a comma-separated list of name-value pairs wrapped in curly braces)
```js
// This is an empty object created using object literal
var myBooks = {};

// This is an object with four items
var mango = {
	color: 'yellow',
	shape: 'round',
	sweetness: 8,
	howSweetAmI: function(){
		console.log('Hmm Good')
	}
}
```
2. Object Constructor(used to initialize new objects)
```js
var mango = new Object();
	mango.color = 'Yellow';
	mango.shape = 'Round';
	mango.sweetness = 8;
	mango.howSweetAmI = function(){
		console.log('Hmm, Good')
	}
```
### How to access object's properties
1. Dot Notation
```js
var books = {
	title: 'Harry Potter',
    pages: 280,
    bookMark: 'Page no: 20'
}

console.log(books.title); // Harry Potter

console.log(books.pages); // 280
```

2. Bracket
```js
console.log ( book["title"]); //Ways to Go​
console.log ( book["pages"]); // 280​
```

### Own and Inherited Properties
Objects have inherited properties and own properties. 

The own properties are properties that were defined on the object. 

The inherited properties were inherited from the object’s Prototype object.

```js
// Create a new school object with a property name schoolName​
​var school = {schoolName:"MIT"};
​
​// Prints true because schoolName is an own property on the school object​
console.log("schoolName" in school);  // true​
​
​// Prints false because we did not define a schoolType property on the school object, and neither did the object inherit a schoolType property from its prototype object Object.prototype.​
console.log("schoolType" in school);  // false​
 
​// Prints true because the school object inherited the toString method from Object.prototype. ​
console.log("toString" in school);  // true
```

### hasOwnProperty
To find out if an object has a specific property as one of its own property, you use the hasOwnProperty method. 
```js
// Create a new school object with a property name schoolName​
​var school = {schoolName:"MIT"};
​
​// Prints true because schoolName is an own property on the school object​
console.log(school.hasOwnProperty ("schoolName"));  // true​
 
​// Prints false because the school object inherited the toString method from Object.prototype, therefore toString is not an own property of the school object.​
console.log(school.hasOwnProperty ("toString"));  // false 
```

### Patterns to create objects

##### 1. Constructor Pattern for Creating Objects
If you applications require to store data, then the above two ways to create objects should be enough for you.
If in other case, where your to create n numbers of fruits, then above methods would be quite tedious. To avoid those hassle, we can use patterns in objects.
For eg:

```js
function fruits(theColor, theSweetness, theFruitName, theNativeLand){
	this.color = theColor;
	this.sweetness = theSweetness;
	this.fruitName = theFruitName;
	this.nativeLand = theNativeLand;

	this.showName = function(){
		console.log('This is a ', this.fruitName)
	}

	this.nativeTo = function() {
		this.nativeLand.forEach(function(eachCountry){
			console.log('Grown in: ', eachCountry);
		});
	}
}

var mango = new Fruit('yellow',8,'mango',['INDIA','USA']);

mango.showName(); // This is a  mango

mango.nativeTo(); // Grown in:  INDIA // Grown in:  USA
```
##### 2. Prototype Pattern for Creating Objects
```js
function Fruit () {
​
}
​
Fruit.prototype.color = "Yellow";
Fruit.prototype.sweetness = 7;
Fruit.prototype.fruitName = "Generic Fruit";
Fruit.prototype.nativeToLand = "USA";
​
Fruit.prototype.showName = function () {
console.log("This is a " + this.fruitName);
}
​
Fruit.prototype.nativeTo = function () {
            console.log("Grown in:" + this.nativeToLand);
}
var mangoFruit = new Fruit ();
mangoFruit.showName(); //​
mangoFruit.nativeTo();
​// This is a Generic Fruit​
​// Grown in:USA
```
[Object's referral link](http://javascriptissexy.com/javascript-objects-in-detail/)