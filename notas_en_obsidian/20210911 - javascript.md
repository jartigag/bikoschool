# Javascript
Versión [ES6](https://262.ecma-international.org/6.0/)

## Arrow functions
```javascript
const d = () => new Date();
const myConcat = (arr, arr2) => arr1.concat(arr2);
console.log(myConcat([1,2],[3,4,5]));
```

## Template literals
```javascript
`<li>${arr[i]}</li>`
```

## Destructuring
```javascript
const {name, age} = user;
```
```javascript
const bicycle = {
	gear: 2,
	setGear(newGear) {
		this.gear = newGear;
	}
};
bicycle.setGear(3);
```

## Spread operator
```javascript
arr2 = [...arr1];
```

## Mixin, IIFE
```javascript
let funModule = (function(){
	return {
		isCuteMixin: function(obj) {
			obj.isCute = function() {
				return true;
			}
		},
		...
	}
})();
```