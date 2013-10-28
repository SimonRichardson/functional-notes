# Compose

------

## 

The `compose` combinator, also known as `B` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper, is a way to apply "Function Composition". By applying one function to the results of another.

------

## Code

### Psuedo code

```
(B f g x) = (f (g x))
```

### Javascript

```javascript
function compose(f) {
	return function(g) {
		return function(c) {
			return f(g(c));
		};
	};
}
```

-----

## Example

### Javascript

The following example uses the compose function to first sort the array, then to reverse it.

```javascript
function a(x) {
	return x.reverse();
}
function b(x) {
	return x.sort();
}
console.log(compose(a)(b)([4, 2, 3, 1])); // Outputs: 4, 3, 2, 1
```

-----

### See

- [flip](flip.md) combinator