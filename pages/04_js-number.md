### for more information  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number

## Number Properties

### EPSILON
EPSILON is a static property of Number, you always use it as Number.EPSILON, 
```javascript
Number.EPSILON // 2.220446049250313e-16 
```

### MAX_SAFE_INTEGER
The Number.MAX_SAFE_INTEGER static data property represents the maximum safe integer in JavaScript (253 – 1).
```javascript
Number.MAX_SAFE_INTEGER // 9007199254740991 
```

### MAX_VALUE
The Number.MAX_VALUE static data property represents the maximum numeric value representable in JavaScript.
```javascript
Number.MAX_VALUE // 1.7976931348623157e+308 
```

### MIN_SAFE_INTEGER
The Number.MIN_SAFE_INTEGER static data property represents the minimum safe integer in JavaScript, or -(253 - 1).
```javascript
Number.MIN_SAFE_INTEGER // -9007199254740991 
```

### MIN_VALUE
The Number.MIN_VALUE static data property represents the smallest positive numeric value representable in JavaScript.
```javascript
Number.MIN_VALUE // 5e-324 
```

### NEGATIVE_INFINITY
The Number.NEGATIVE_INFINITY static data property represents the negative Infinity value.
```javascript
Number.NEGATIVE_INFINITY // -Infinity 
```

### NaN
Because NaN is a static property of Number, you always use it as Number.NaN, rather than as a property of a number value.
```javascript
Number.NaN // NaN 
```

### POSITIVE_INFINITY
The Number.POSITIVE_INFINITY static data property represents the positive Infinity value.
```javascript
Number.POSITIVE_INFINITY // Infinity 
```

## Number methods

### toString()
The toString() method returns a number as a string.
```javascript
let num = 5
num.toString() // "5" 
```

### toLocaleString()
The toLocaleString() method of Number values returns a string with a language-sensitive representation of this number. 
```javascript
let num = 7.1835 
num.toLocaleString() // "7.184"
num.toLocaleString("zh-Hans-CN-u-nu-hanidec") // "七.一八四" 
```

### toExponential()
The toExponential() method of Number values returns a string representing this number in exponential notation. 
```javascript
let num = 7.1835
num.toExponential() // "7.1835e+0"
num.toExponential(2) // "7.18e+0" 
```

### toFixed()
The toFixed() method of Number values formats this number using fixed-point notation.
```javascript
let num = 7.1835
num.toFixed() // "7"
num.toFixed(2) // "7.18" 
```

### toPrecision()
The toPrecision() method of Number values returns a string representing this number to the specified precision. 
```javascript
let num = 10.5162
num.toPrecision() // "10.5162"
num.toPrecision(4) // "10.52" 
```

### valueOf()
The valueOf() method of Number values returns the value of this number.
The valueOf() method is used internally in JavaScript to convert Number objects to primitive values.
```javascript
let num = new Number(5)
num.valueOf() // 5 
```