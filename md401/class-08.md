# List Comprehensions

In order to keep your code elegant and readable, it’s recommended that you use Python’s comprehension features.

List comprehension is a powerful and concise method for creating lists in Python that becomes essential the more you work with lists, and lists of lists.

## Notes about Lists Comprehensions

- List comprehension methods are an elegant way to create and manage lists.
- In Python, list comprehensions are a more compact way of creating lists.
- More flexible than for loops, list comprehension is usually faster than other methods.

### Create a List with range()

```py
digits = [x for x in range(10)]
print(digits)
```

```py
# output [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### Create a List Using Loops and List Comprehension in Python

### Parsing a file using list comprehension

- Hold fast to dreams
- For if dreams die
- Life is a broken-winged bird
- That cannot fly.
- Langston Hughes

     Reading a poem with list comprehensions

```py
# open the file in read-only mode
file = open("dreams.txt", 'r')
poem = [ line for line in file ]

for line in poem:
    print(line)
```

Output

```py
'''
Hold fast to dreams

For if dreams die

Life is a broken-winged bird

That cannot fly.

-Langston Hughs
'''
```

### List comprehension offers a shorter syntax when you want to create a new list based on the values of an existing list.