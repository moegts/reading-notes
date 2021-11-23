# Automation

## Python Regular Expression Tutorial

Regular Expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not. If you've ever used search engines, search and replace tools of word processors and text editors - you've already seen regular expressions in use. They are used at the server side to validate the format of email addresses or passwords during registration, used for parsing text data files to find, replace, or delete certain string, etc. They help in manipulating textual data, which is often a prerequisite for data science projects involving text mining.

```py
# Regular Expressions in Python
import re

# Basic Patterns: Ordinary Characters
pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")

## res: Match!

# Wild Card Characters: Special Characters
re.search(r'Co.k.e', 'Cookie').group()
## res: 'Cookie'


## This is helpful if you want to make sure a document/sentence starts with certain characters.

re.search(r'^Eat', "Eat cake!").group()

## However, the code below will not give the same result. Try it for yourself:
# re.search(r'^eat', "Let's eat cake!").group()

## res: 'Eat'

re.search(r'cake$', "Cake! Let's eat cake").group()

## The next search will return the NONE value, try it:
# re.search(r'cake$', "Let's get some cake on our way home!").group()

## res: 'cake'

# Repetitions
## + - Checks if the preceding character appears one or more times starting from that position.
re.search(r'Co+kie', 'Cooookie').group()
## res: 'Cooookie'

```

## shutil: to read about it please vist [shutil](https://pymotw.com/3/shutil/)

its like cheat sheet so if i want to note it i would copy all of it
i did read alot of it and planing to read more...
