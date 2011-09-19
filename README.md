The Specification Pattern in JavaScript
==============================
Define a specification.
------------------------------
```javascript
// no odd numbers allowed!
var even = spec(function (candidate) {
    return 0 === candidate % 2;
});
```
Negate that guy and save him for later.
----------------------------------------------------
```javascript
// negate even to get an odd future
var odd = even.not();
```
Maybe get a little fancy with it.
----------------------------------------
```javascript
// detest negativity
var positive = spec(function (candidate) {
    return candidate > 0;
});

// evenly positive
var evenAndPositive = even.and(positive);

// odd or positive
var oddOrPositive = odd.or(positive);
```
Quench your thirst for truthiness.
---------------------------------------------
```javascript
console.log(even.isSatisfiedBy(3)); // false
console.log(odd.isSatisfiedBy(3)); // true
console.log(evenAndPositive.isSatisfiedBy(-2)); // false
console.log(oddOrPositive.isSatisfiedBy(2)); // true
```