# React and Forms

## React Docs - Forms

- Controlled Component

### component that renders form elements and controls them by keeping the form data in the component's state.

- Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.

### We wait until submit because if they change the input before submit so storing all their tries will end up being impractical.

- How do we target what the user is entering if we have an event handler on an input field?

### `event.target.userInput`

## The Conditional (Ternary) Operator Explained

- Why would we use a ternary operator?

### A ternary operator allows you to assign one value to the variable if the condition is true, and another value if the condition is false, The if else block example from above could now be written as shown in the example below.

- Rewrite the following statement using a ternary statement:

```js
  if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }
```

### solved

```js
msg = "";
if (x === y) {
  msg = true;
}
else {
  msg = false;
}
console.log(msg);
```

## Things I want to know more about

- React Bootstrap