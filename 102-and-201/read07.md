# Programming with JavaScript

![Programming with JavaScript](prJs.png)

## Java Script Functions

#### The **JavaScript** function is a block of code that was made to perform a particular task. ​
#### And it’s executed when there’s something that invokes it (calls it).

#### For an example:

```
Function myFunction(p1, p2)  { ​
    return p1  *  p2;       //  The function returns the product of p1 and p2 
```
## JavaScript Function Syntax

#### A JavaScript function is defined with the function keyword and followed by a name, followed by parentheses ().

#### It may include parameter names separated by commas:   Parameter 1 & Parameter 2, etc…)

```
Function name(Parameter1, Parameter2,Parameter3)  {​
     //  code to be executed 
```
## Function invocation 

#### The code inside the function will execute when “something” invokes (calls) the function : 

- When an event occurs ( when a user clicks a button )
- When it’s invoked ( Called ) From JavaScript
- Automatically ( Self invoked )

## Function Return

#### When the JavaScript reaches the return statement, The function will stop executing.

#### If the function was invoked from a statement, the Java Script will “Return” To execute the code after the invoking statement. 

#### Functions often compute a Return Value. The return value is “returned” back to the “caller” :

#### For an example :

```
Calculate : let x = myFunction(4,  3);     //  function is called, return value will end up in x​
​
​
function myfunction(a,   b)   {​
​
    return a   *   b;                                      //   function returns the product of a and b ​
}​
​
so the result in x will be :  12​
```