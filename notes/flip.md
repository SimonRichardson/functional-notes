# Flip

## Reference

The `flip` combinator, also known as `C` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper. Flipping the arguments of a function when calling a [composable](compose.md) function.


## Code

### Pseudo code

```
(C f x y) = (f y x)
```

### Javascript

```javascript
function flip(f) {
    return function(a) {
        return function(b) {
            return f(b)(a);
        };
    };
}
```

## Example

The following example uses the flip combinator to first capture the compose combindator then call reverse; then sort. The reverse function is called first, then sort function because the arguments are flipped via the combinator.

```javascript
function a(x) {
	return x.reverse();
}
function b(x) {
	return x.sort();
}
console.log(flip(compose)(a)(b)([4, 2, 3, 1])); // Outputs: 1, 2, 3, 4
```

## See

- [Compose](compose.md) combinator