# Apply

## Reference

The `apply` combinator, also known as `A` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper. Applies the argument of the second function call to the function.

## Code

### Psuedo code

```
(A f x) = (f x)
```

### Javascript

```javascript
function apply(f) {
    return function(x) {
        return f(x);
    };
}
```

## Example

The following example uses the flip combinator to first capture the compose combindator then call reverse; then sort. The reverse function is called first, then sort function because the arguments are flipped via the combinator.

```javascript
function inc(x) {
	return x + 1;
}
console.log(apply(inc)(1)); // Outputs: 2
```