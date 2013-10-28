# Thrush

## Reference

The `thrush` combinator, also known as `T` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper. Using the argument of the first function (`x`) call to be applied to the function of the second (`f`).

### Notes: 

This is very similar to the Apply combinator, except the arguments are swapped, where the function is the first argument.


## Code

### Psuedo code

```
(C f x y) = (f y x)
```

### Javascript

```javascript
function thrush(x) {
    return function(f) {
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
console.log(thrush(1)(inc)); // Outputs: 2
```

## See

- [Apply](apply.md) combinator