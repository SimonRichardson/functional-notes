# Identity

## Reference

The `identity` combinator, also known as `I` Combinator from [Schönfinkel](http://en.wikipedia.org/wiki/Moses_Sch%C3%B6nfinkel)'s paper. Considered one of the simplist combinators, the identity combinator is defined as: 

#### Notes:

Identity is considered both Idempotent and Referential Transparent.

## Code

### Pseudo code

```
(I x) = x
```

### Javascript

```javascript
function identity(x) {
    return x;
}
```

## Example

The following example uses the flip combinator to first capture the compose combindator then call reverse; then sort. The reverse function is called first, then sort function because the arguments are flipped via the combinator.

```javascript
console.log(identity(1)); // Outputs 1
```

## See

- [Idempotent Functions](idempotent-function.md)
- [Referential Transparent](referential-transparent.md)