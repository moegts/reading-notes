# Topic

## Classes and Objects

- Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.

- A very basic class would look something like this:
  
```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")
```

- assign the above class(template) to an object:

```py
myobjectx = MyClass()
```

- Accessing Object Variables:

```py
myobjectx.variable
```

- Accessing Functions inside Object:

```py
myobjectx.function()
```

## Recursive Functions in Python

### Maintaining State

When dealing with recursive functions, keep in mind that each recursive call has its own execution context, so to maintain state during recursion you have to either:

  - Thread the state through each recursive call so that the current state is part of the current call’s execution context
  - Keep the state in global scope

## Python Testing with pytest

pytest allows you to become better at testing your code

### Fixtures

In pytest, you define fixtures using a combination of the pytest.fixture decorator, along with a function definition. For example, say you have a file that returns a list of lines from a file, in which each line is reversed:

```py
def reverse_lines(f):
   return [one_line.rstrip()[::-1] + '\n'
           for one_line in f]
```

Here's how that looks in pytest:

```py
@pytest.fixture
def simple_file():
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))
```

### Summary

If you haven't guessed from my three-part focus on pytest, I've been bowled over by the way this testing system has been designed. After years of hanging my head in shame when talking about testing, I've started to incorporate it into my code, including in my online "Weekly Python Exercise" course. If I can get into testing, so can you. And although I haven't covered everything pytest offers, you now should have a good sense of what it is and how to start using it.
