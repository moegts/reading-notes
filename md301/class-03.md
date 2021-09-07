# Passing Functions as Props

## React Docs - lists and keys

- What does .map() return?

### map() function returns a map object(which is an iterator) of the results after applying the given function to each item of a given iterable (list, tuple etc.)

- If I want to loop through an array and display each value in JSX, how do I do that in React?

### use `.map()`

### Each list item needs a unique ____.

1. use `.map()`
2. create new array to push on it the map function value
3. return the array or render it as you want

## The Spread Operator

- spread operator

### Spread operator allows an iterable to expand in places where 0+ arguments are expected

- 4 things that the spread operator can do.

1. Copying an array.
2. Concatenating or combining arrays.
3. Using Math functions.
4. Using an array as arguments

- an example of using the spread operator to combine two arrays.

```js
let bmw = ['M3', 'M5'];
let dodge = ['challenger', 'viper'];

let cars = [...bmw, ...dodge];
// or we can put the first array at the end it dosent matter
let cars = [...dodge,...bmw];
```

- an example of using the spread operator to add a new item to an array.

```js
let a = [1, 2, 3, 4, 5];
let b = [0, ...a];
```

- an example of using the spread operator to combine two objects into one.

```js
let person = {
    firstName: 'Moe',
    lastName: 'Ali',
    age: 29,
};

let job = {
    jobTitle: 'Developer',
    location: 'Jordan'
};

let employee = {
    ...person,
    ...job
};

// employee it will be like this

employee = {
    firstName: 'Moe',
    lastName: 'Ali',
    age: 29,
    jobTitle: 'Developer',
    location: 'Jordan'}
```

- In the video, what is the first step that the developer does to pass functions between components?

### passed function as a prop from higher to lower component

- what does the `increment` function do?

### determines the next node at the same level

- In the higher element Pass it to lower component as a prop by render method.
- In the lower component in the state call that method as value prop `this.props.function(this.props.parameter);` then Add this function to the event handler

- - -

- How does the child component invoke a method that was passed to it from a parent component?

### 