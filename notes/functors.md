# Functors

## Reference

A functor is a type of mapping between categories, with that; `Functors` are basically types that can be mapped over. `Functors` will always return the same `Functor` type, but the value internal may have been mapped (changed) revealing a new value. 

## Code

### Psuedo code

```
f(a -> b) -> f a -> f b
```

### Javascript

```javascript
var Functor = function(val) {
    this.val;
};
Functor.prototype.fmap = function(f) {
    return Functor(f(this.val));
};
```

### Types of Functors

There are many types of functors, here are some others:

#### Covariant functor

Covariant functors - defines the operation commonly known as `map` or `fmap`.

```
f(a -> b) -> f a -> f b
```

#### Contravariant functor

Contravariant functors - defines the operation commonly known as `contramap`.

```
f(b -> a) -> f a -> f b
```

## Example

Introducting the `Maybe` type, which says that whatever context our function is mapping over might or it might not. If it does contain a value then run the function against it, but if it doesn't then don't run the function at all and return the Maybe back. This is a really handy little functor as it's basically an abstracted null check that we can map over!

```javascript
var Maybe = function(val) {
    this.val = val;
};
Maybe.prototype.fmap = function(f) {
    return this.val ? Maybe(f(this.val)) : Maybe(null);  
};
console.log(Maybe(3).fmap(function(x) {
    return x + 1;
})); // Outputs: Maybe(4)
```

## See

- [Monads](monads.md) Monads
- [Taking Things Out of Context: Functors](https://medium.com/the-javascript-collection/d80b4c94b90f)
- [Making Our Own Types and Typeclasses](http://learnyouahaskell.com/making-our-own-types-and-typeclasses#the-functor-typeclass)
- [Functors, Applicative Functors and Monoids](http://learnyouahaskell.com/functors-applicative-functors-and-monoids)