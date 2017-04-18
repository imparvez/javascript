# Chp 02: JavaScript's Variable Scope and Hoisting

Variable Scope:
It is a context in which the variable exists.
Variable have two types of scope:
	* Local Scope
	* Global Scope

### Local Variable:
JavaScript is not block level scoped language instead it is a function level scoped language.
Variables defined within a function are local variables and are only accessible within that function or function inside that function.

Function Level Scope

```js
var car = "Ford";

function showCarName(){
	var car = "Aston Martin";
	console.log(car); // Aston Martin => Local Variable
}

console.log(car); // Ford => The global variable
```

*Note: * Variable declared without var keywords become Global Variable.

##### You should always declared your local variable

```js
var car = "Ford";

function showName(){
	console.log(car);
}

function showOtherName(){
	car = "Aston Martin";
	console.log(car);
}

showName();


showOtherName();


showName();

function showOtherName(){
	var car = "Ferrari";
	console.log(car);
}

``

##### Local Variables have high priority over global variable

```js
var car = "Ford";

function showName(){
	var car = "Aston Martin";
	console.log(car);
}

showName(); // Aston Martin

```

### Global Variable
Variables that are declared outside a function are in the global scope.

	* Any Variable declared or initialized outside a function is a global variable and it available to entire function.
	```js
	var myName = "Parvez";

	// OR

	firstName = "Parvez";
	```

	* If variable is initialized without first being declared with var keyword, it is automatically added to global context.
	```js
	function showCarMileage(){
		carMileage = 30;
		console.log(carMileage);
	}

	showCarMileage(); // 30

	console.log(carMileage); // 30
	```

	* setTimeout Variables are executed in global scope
	```js
	var highValue = 200;
	var constValue = 2;

	var myObj = {
		highValue: 20,
		constValue: 5,
		cal: function(){
			setTimeout(function(){
				console.log(this.highValue * this.constValue)	
			}, 2000)
		}
	}
	​// The "this" object in the setTimeout function used the global highValue and constantVal variables, because the reference to "this" in the setTimeout function refers to the global window object, not to the myObj object as we might expect.​
​
	myObj.cal(); // 400​

	```


[JavaScript Variable Scope and Hoisting Explained](http://javascriptissexy.com/javascript-variable-scope-and-hoisting-explained/)