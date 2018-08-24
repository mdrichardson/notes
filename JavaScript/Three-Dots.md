# Three Dots/Spread Syntax

Three dots (`...`) can be used in Javascript to clone objects and arrays into new ones, with changes.

## Objects

For example, if you have an object:

```javascript
fred = {
    name:  'Fred',
    age: 40,
    sex: 'Male',
    species: 'Human'
}
```

You can quickly create a near-duplicate by using:

```javascript
john = {
    ...fred,
    name: 'John',
    age: 24
}
```

This would result in:

```javascript
john = {
    name:  'John',
    age: 24,
    sex: 'Male',
    species: 'Human'
}
```

## Arrays

With arrays, if you have:

```javascript
numbers = [1, 2, 3]
```

You can add those into a new array using:

```javascript
all_numbers = [...numbers, 4, 5, 6]
```

This results in:

```javascript
all_numbers = [1, 2, 3, 4, 5, 6]
```

## Functions

You can also use it in arguments of a function to allow unlimited numbers of arguments to be passed in. This is similar to accepting an array, but this allows you to accept either an array *or* multiple arguments.

```javascript
function sum(...numbers) {
    return numbers.reduce((accumulator, current) => {
        return accumulator += current
    });
};

sum(1,2) // 3
sum(1,2,3,4,5) // 15
```