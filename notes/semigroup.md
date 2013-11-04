# Semigroup

## Reference

A `semigroup` is an type consisting of a set together with an associative binary operation. A `semigroup` generalizes a `monoid` in that a `semigroup` need not have an identity element

Generally speaking a `semigroup` contains a `append` method,

* Closure: ∀ a, b in S, append(a, b) is also in S. This is enforced by the type system.
* Associativity: ∀ a, b and c in S, the equation append(append(a, b), c) = append(a, append(b , c)) holds.

## Code

### Pseudo code

```
∀ a, b
```

### Javascript

```javascript
var Semigroups = function(val) {
    this.val = val;
};
Semigroups.prototype.append = function(b, f) {
    return f(this.val, b);
};
```

## Example

Introducing the `Maybe` type, which says that whatever context our function is mapping over might or it might not. If it does contain a value then run the function against it, but if it doesn't then don't run the function at all and return the Maybe back. This is a really handy little functor as it's basically an abstracted null check that we can append over!

```javascript
var Maybe = function(val) {
    this.val = val;
};
Maybe.prototype.append = function(b, f) {
    return this.val ? Maybe(f(this.val, b)) : Maybe(null);  
};
console.log(new Maybe(3).append(new Maybe(2), function(x, y) {
    return x + y;
})); // Outputs: Maybe(5)
```

## See

- [Monoids](monoids.md)