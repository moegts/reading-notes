# JS Debugging 

## JavaScript book, Ch. 10, “Error Handling & Debugging”


### ORDER OF EXECUTION 


### WRITING FROM THE SCRIPT TO THE CONSOLE 

#### Browsers that have a console have a console object, which has several methods that your script can use to display data in the console. The object is documented in the Console API. 

#### If you know something might cause a problem for your script, you can generate your own errors before the interpreter creates them. 


### CONDITIONAL BREAKPOINTS

#### You can indicate that a breakpoint should be triggered only if a condition that you specify is met. The condition can use existing variables. 

- If you understand execution contexts (which have two stages) and stacks, you are more likely to find the error in your code.

- Debugging is the process of finding errors. It involves a process of deduction.

- The console helps narrow down the area in which the
error is located, so you can try to find the exact error. 

- JavaScript has 7 different types of errors. Each creates
its own error object, which can tell you its line number
and gives a description of the error. 

- If you know that you may get an error, you can handle
it gracefully using the try, catch, finally statements.
Use them to give your users helpful feedback.

