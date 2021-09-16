# memory storage

- What is a ‘call’?

## The call stack maintains a record of the position of each stack frame. It knows the next function to be executed (and will remove it after execution). This is what makes code execution in JavaScript synchronous.

- How many ‘calls’ can happen at once?

## One call

- What does LIFO mean?

## Last In, First Out - it is a data structure principle in which the last function that gets pushed into the stack is the first to be popped out, when the function returns.

- Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

[example of a call stack](./imgs/301r10.png)

- What causes a Stack Overflow?

## when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

- - -

## JavaScript error messages

- What is a ‘refrence error’?

## when you try to use a variable that is not yet declared you get this type os errors.

- What is a ‘syntax error’?

## An exception caused by the incorrect use of a pre-defined syntax.

- What is a ‘range error’?

## A RangeError is thrown when trying to pass a value as an argument to a function that does not allow a range that includes the value.

- What is a ‘tyep error’?

## The TypeError object represents an error when an operation could not be performed, typically (but not exclusively) when a value is not of the expected type.

- What is a breakpoint?

## ‏Use breakpoints to pause your JavaScript code. This guide explains each type of breakpoint that's available in DevTools,

- What does the word ‘debugger’ do in your code?

## The debugger keyword stops the execution of JavaScript, and calls (if available) the debugging function.
