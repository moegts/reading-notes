# global and nonlocal

- The Python scope concept is generally presented using a rule known as the LEGB rule.

- Understanding Scope

In programming, the scope of a name defines the area of a program in which you can unambiguously access that name, such as variables, functions, objects, and so on.
 A name will only be visible to and accessible by the code in its scope.
Several programming languages take advantage of scope for avoiding name collisions and unpredictable behaviors.
Most commonly, you’ll distinguish two general scopes:

- **Global scope**: The names that you define in this scope are available to all your code.

- **Local scope**: The names that you define in this scope are only available or visible to the code within the scope.

- Names and Scopes in Python
Since Python is a dynamically-typed language, variables in Python come into existence when you first assign them a value. On the other hand, functions and classes are available after you define them using def or class, respectively

## Using the LEGB Rule for Python Scope

1. Local (or function)
2. Enclosing (or nonlocal)
3. lobal (or module) scope
4. Built-in scope

## **Nested Functions**: The Enclosing Scope

Enclosing or nonlocal scope is observed when you nest functions inside other functions. The enclosing scope was added in Python 2.2. It takes the form of the local scope of any enclosing function’s local scopes. Names that you define in the enclosing Python scope are commonly known as nonlocal names

## **Functions**: The Local Scope

Every time you call a function, you’re also creating a new local scope. On the other hand, you can think of each def statement and lambda expression as a blueprint for new local scopes. These local scopes will come into existence whenever you call the function at hand.


## **Modules**: The Global Scope

From the moment you start a Python program, you’re in the global Python scope. Internally, Python turns your program’s main script into a module called __main__ to hold the main program’s execution. The namespace of this module is the main global scope of your program.

- - -

Good programming practice recommends using local names rather than global names. Here are some tips:

- Write self-contained functions that rely on local names rather than global ones.
- Try to use unique objects names, no matter what scope you’re in.
- Avoid global name modifications throughout your programs.
- Avoid cross-module name modifications.
Use global names as constants that don’t change during your program’s execution.

## The nonlocal Statement

Similarly to global names, nonlocal names can be accessed from inner functions, but not assigned or updated. If you want to modify them, then you need to use a nonlocal statement. With a nonlocal statement, you can define a list of names that are going to be treated as nonlocal.

## **The global Statement**

You already know that when you try to assign a value to a global name inside a function, you create a new local name in the function scope. To modify this behavior, you can use a global statement. With this statement, you can define a list of names that are going to be treated as global names.

## **Using Enclosing Scopes as Closures**

When you handle a nested function as data, the statements that make up that function are packaged together with the environment in which they execute.
The resulting object is known as a closure.
In other words, a closure is an inner or nested function that carries information about its enclosing scope, even though this scope has completed its execution.

## **Discovering Unusual Python Scopes**

You’ll find some Python structures where name resolution seems not to fit into the LEGB rule for Python scopes. These structures include:

- **Comprehensions**
- **Exception blocks**
- **Classes and instances**

## **Class and Instance Attributes Scope**

When you define a class, you’re creating a new local Python scope. The names assigned at the top level of the class live in this local scope. The names that you assigned inside a class statement don’t clash with names elsewhere. You can say that these names follow the LEGB rule, where the class block represents the L level.

## **Using Scope Related Built-In Functions**

1- **`globals()`**: 
is a built-in function that returns a reference to the current global scope or namespace dictionary

2- **`locals()`**:
This function updates and returns a dictionary that holds a copy of the current state of the local Python scope or namespace.

3- **`dir()`**:
to get the list of names in the current Python scope

4- **`vars()`**:
vars() is a Python built-in function that returns the .
__dict__ attribute of a module, class, instance, or any other object.

## Conclusion

The scope of a variable or name defines its visibility throughout your code.
In Python, scope is implemented as either a Local, Enclosing, Global, or Built-in scope. When you use a variable or name, Python searches these scopes sequentially to resolve it.
If the name isn’t found, then you’ll get an error.
This is the general mechanism that Python uses for name resolution and is known as the LEGB rule.
