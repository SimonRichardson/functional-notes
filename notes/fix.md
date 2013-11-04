# Fix

## Reference

The `fix` combinator, also known as `Y` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper. A `Y` combinator is a function that generalizes recursion.

#### Notes

The goal is to be able to write a recursive function of 1 variable using only functions of 1 arity and no assignments, defining things by name.

The `Y` combinator can be expressed in the [SKI-calculus](http://en.wikipedia.org/wiki/SKI_combinator_calculus) as: ```Y = S (K (S I I)) (S (S (K S) K) (K (S I I)))```


## Code

### Pseudo code

```
Y = λf.(λx.f (x x)) (λx.f (x x))
```

### Javascript

```javascript
function fix(f) {
    function g(h) {
        return function(x) {
            return f(h(h))(x);
        };
    }
    return g(g);
}
```

## Example

```javascript
// TODO
```

## See

- [Constant](constant.md) combinator
- [Identity](identity.md) combinator
- [Substitution](substitution.md) combinator

