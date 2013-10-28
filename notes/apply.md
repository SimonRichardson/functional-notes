# Apply

## Reference

The `apply` combinator, also known as `A` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper. Applies the argument of the second function call to the function.

### Notes: 

This is very similar to the Thrush combinator, except the arguments are swapped, where the function is the second argument.

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

The following example applies the value of `1` to the function of `inc`, with the sole purpose in incrementing the `x` value by `1`.

```javascript
function inc(x) {
	return x + 1;
}
console.log(apply(inc)(1)); // Outputs: 2
```

## See

- [Thrush](thrush.md) combinator