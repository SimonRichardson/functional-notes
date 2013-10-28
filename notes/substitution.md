# Substitution

## Reference

The `substitution` combinator, also known as `S` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper. 

#### Notes

`S` Combinator is a sort of generic substitution generator

## Code

### Psuedo code

```
(S x y z) = (x z (y z))
```

### Javascript

```javascript
function substitution(f) {
    return function(g) {
        return function(x) {
            f(x)(g(x));
        };
    };
}
```

## Example

This example is quite contrived (this could be replaced with one that is better suited). The example will run `inc` first, by incrementing `1` to the argument, then it will call `dec` to the newly incremented value (in this case `2`) and return `1`.


```javascript
function dec(x) {
	return x - 1;
}
function inc(x) {
	return x + 1;
}
console.log(substitution(constant(dec))(inc)(1)); // Outputs: 1
```

## See

- [Constant](constant.md) combinator
- [Fix](fix.md) combinator