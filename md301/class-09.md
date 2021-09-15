# FUNCTIONAL PROGRAMMING

## Functional Programming Concepts

- What is functional programming?

### is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data

- What is a pure function and how do we know if something is a pure function?

### It returns the same result if given the same arguments (it is also referred as deterministic)

### It does not cause any observable side effects

### Pure functions take some input and return some output based on that input. They are the simplest reusable building blocks of code in a program

- What are the benefits of a pure function?

### code’s definitely easier to test. We don’t need to mock anything

- What is immutability?

### its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value

- What is Referential transparency?

### pure functions + immutable data = referential transparency

- What is a module?

### Modules are the blocks of encapsulated code that communicates with an external application on the basis of their related functionality. Modules can be a single file or a collection of multiples files/folders.

- What does the word ‘require’ do?

### require function is the easiest way to include modules that exist in separate files.

- How do we bring another module into the file the we are working in?

### we need to import the module. we will use the require keyword at the top of the file. The result of require is then stored in a variable which is used to invoke the functions using the dot notation

- What do we have to do to make a module available?

### In order to make modules available to the Node.js REPL, it might be useful to also add the /usr/lib/node_modules folder to the $NODE_PATH environment variable. Since the module lookups using node_modules folders are all relative, and based on the real path of the files making the calls to require(), the packages themselves can be anywhere.