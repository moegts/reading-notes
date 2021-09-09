# Putting it all together

## React Docs - thinking in React

- How would you break a mock into a component heirarchy?

### draw boxes around every component (and subcomponent) in the mock and give them all names. If you’re working with a designer, they may have already done this, so go talk to them! Their Photoshop layer names may end up being the names of your React components

- What is the single responsibility principle and how does it apply to components?

### a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.

- What does it mean to build a ‘static’ version of your application?

### build components that reuse other components and pass data using props. props are a way of passing data from parent to child. If you’re familiar with the concept of state, don’t use state at all to build this static version.

- What are the three questions you can ask to determine if something is state?

1. Can it be passed in from a parent via props? the state does not pass.
2. Remain unchanged over time? the state does not remain unchanged over time.
3. Can we compute it based on any other state or props in the component? the state does not compute.

- How can you identify where state needs to live?

### follow these steps to figure it out:-

1. Identify every component that renders something based on that state.
2. Find a common owner component (a single component above all the components that need the state in the hierarchy).
3. Either the common owner or another component higher up in the hierarchy should own the state.
4. If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

## Things I want to know more about
[Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
