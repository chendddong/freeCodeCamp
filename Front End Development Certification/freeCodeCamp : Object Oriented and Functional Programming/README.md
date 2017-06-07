# Some Good Points

### Construct JavaScript Objects with Functions
```javascript
var Car = function() {
  this.wheels = 4;
  this.engines = 1;
  this.seats = 5;
};

var MotorBike = function() {
  this.wheels = 2;
  this.engines = 1;
  this.seats = 3;
};
```

### Make Instances of Objects with a Constructor Function
```javascript
var Car = function() {
  this.wheels = 4;
  this.engines = 1;
  this.seats = 5;
};

var myCar = new Car();
myCar.nickname = "Chipper";
```

### Make Unique Objects by Passing Parameters to our Constructor
```javascript
var Car = function(wheels, seats, engines) {
  this.wheels = wheels;
  this.seats = seats;
  this.engines = engines;
};

var myCar = new Car(4, 7, 3);
```

### Make Object Properties Private
To do this, we create the variable inside the constructor using the ***var***
keyword we're familiar with, instead of creating it as a property of
***this***.This is useful for when we need to store information about an object but we want to control how it is used by outside code.
```javascript

var Car = function() {
  // this is a private variable
  var speed = 10;

  // these are public methods
  this.accelerate = function(change) {
    speed += change;
  };

  this.decelerate = function() {
    speed -= 5;
  };

  this.getSpeed = function() {
    return speed;
  };
};

var Bike = function() {

  // Only change code below this line.
  var gear;
  this.getGear = function() {
    return this.gear;
  };
  this.setGear = function(value) {
    this.gear = value;
  };
};

var myCar = new Car();

var myBike = new Bike();

```
### Iterate over Arrays with map

The map method will iterate through every element of the array, creating a new array with values that have been modified by the callback function, and return it. Note that it does not modify the original array.

In our example the callback only uses the value of the array element (the val argument) but your callback can also include arguments for the index and array being acted on.

```javascript
var oldArray = [1,2,3,4,5];
var newArray = oldArray.map(function(val) {
  return val += 3;
});

```

### Condense arrays with reduce
reduce has an optional second argument which can be used to set the initial value of the accumulator. If no initial value is specified it will be the first array element and currentVal will start with the second array element.
Here is an example of reduce being used to subtract all the values of an array:

>var singleVal = array.reduce(function(previousVal, currentVal) {
  return previousVal - currentVal;
}, 0);

Use the reduce method to sum all the values in array and assign it to singleVal.

```javascript
var array = [4,5,6,7,8];
var singleVal = 0;

singleVal = array.reduce(function(privousVal, currentVal) {
  return privousVal + currentVal;  
});
```

### Filter Arrays with filter
```javascript
var oldArray = [1,2,3,4,5,6,7,8,9,10];
var newArray = oldArray.filter(function(val) {
  return val < 6;
});
// newArray = [1,2,3,4,5]
```
### Sort Arrays with sort
```javascript
var array = [1, 12, 21, 2];
// the function inside is like a comparator in Java
array.sort(function(a,b) {
  return b - a; // descending order
});
```

### Reverse Arrays with reverse
```javascript
var array = [1,2,3,4,5,6,7];
var newArray = [];
newArray = array.reverse();
```

### Concatenate Arrays with concat
```javascript
var oldArray = [1,2,3];
var newArray = [];
var concatMe = [4,5,6];
newArray = oldArray.concat(concatMe);
```

### Split Strings with split
Here is an example of split being used to split a string at every s character:
>var array = string.split('s');

```javascript
var string = "Split me into an array";
var array = [];
array = string.split(' ');
```

### Join Strings with join
The following is an example of using join to join all of the elements of an array into a string with all the elements separated by word and:
```javascript
var veggies = ["Celery", "Radish", "Carrot", "Potato"];
var salad = veggies.join(" and ");
console.log(salad); // "Celery and Radish and Carrot and Potato"
```
```javascript
var joinMe = ["Split","me","into","an","array"];
var joinedString = '';
joinedString = joinMe.join(" ");
```




