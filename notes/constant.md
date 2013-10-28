# Constant

## Reference

The `constant` combinator, also known as `K` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper. Creates a constant function that for any argument always returns the first (`x` in this case)

## Code

### Psuedo code

```
((K x) y) = x
```

### Javascript

```javascript
function constant(a) {
	return function(b) {
		return a;
	};
}
```

## Example

The following example uses the constant combinator to create a function which always returns 1, no matter what the second argument is. 

```javascript
console.log(constant(1)(2)); // Outputs: 1
```

This useful for always returning `false`, `true` from a function. Consider:

```javascript
function alwaysFalse() {
	return constant(false);
}
console.log(alwaysFalse()(true)); // Outputs: false
```



