# ES2016
A breif quick and dirty run through for getting a taste of the ES2016 JavaScript

The additions of ES2016 are light

## Array.protoype.includes

The array type now has an includes method built into it. This method searching through the array much like `indexOf` but instead of returning an index number, it will return a Boolean to the caller.

### Examples

```js
['a', 'b', 'c'].includes('c'); // => true

['a', 'b'].includes('c'); // => false
```

Comparing complex types Note here that these are EMPTY objects

```js
[{}, {}].includes({}); // => false

const a = {};

[{}, a].includes(a); // => true
```

This is a simple check which passes because the variable `a` takes up the same memory in this case meaning it is comparable

You can also specify a point to start your search with a second parameter

```js
['a', 'b', 'c', 'd'].includes('a', 1); // => false
```

Even though you can't compare `NaN` types so `NaN !== NaN` `.includes` uses the [`SameValueZero` comparison algorithm](http://www.ecma-international.org/ecma-262/6.0/#sec-samevaluezero) where `NaN` is actually equivalent to itself.

```js
[NaN].includes(NaN); // => true
```

And that's about it for the includes method.


## Exponentiation Operator (**)

The exponentiation operator – or a ** b – is the syntactic equivalent to doing Math.pow(a, b). It’ll work similarly to the [exponentiation operator in Python](http://www.pythonforbeginners.com/basics/python-operators).

### Examples

```js
1 ** 2 === Math.pow(1, 2); // => true
```

Just like with any other operators, it’s possible to mix exponentiation with assignment, as show below.

```js
let a = 2;
a **= 3; // equivalent to a = Math.pow(a, 3)
console.log(a); // => 8
```

## Conclusion

So that about does it for ES2016 pretty simple and much smaller than ES2015 additions right?
