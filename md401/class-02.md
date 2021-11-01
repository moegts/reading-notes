# Testing and Modules

## In Tests We Trust - TDD with Python

introduction of TDD with Python and how to do unit tests and how to refactor safely.

- Unit tests and TDD - The cycle is made by three steps:-

1. 🆘 Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)
2. ✅ Write the feature and make the test pass! (you can dance after that)
3. 🔵 Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)

- TDD is not about the money/tests
building what is needed to make the test pass. When we are writing tests we are forced to think about the design first and how we can break it into small pieces.

## If name equals main

```py
print ("Always executed")
 
if __name__ == "__main__":
    print ("Executed when invoked directly")
else:
    print ("Executed when imported")
```

## Advantages:-

1. Every Python module has it’s __name__ defined and if this is ‘__main__’, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.
2. If you import this script as a module in another script, the __name__ is set to the name of the script/module.
3. Python files can act as either reusable modules, or as standalone programs.
4. if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported.

## Recursion:-

every recursive program can be written iteratively and vice versa is also true. The recursive program has greater space requirements than iterative program as all functions will remain in the stack until the base case is reached. It also has greater time requirements because of function calls and returns overhead.
