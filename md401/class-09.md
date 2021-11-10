# Dunder Methods & Statistics - Probability

## Dunder Methods (Magic Methods)

set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.

### Enriching a Simple Account Class

- Initialization of new objects
- Object representation
- Enable iteration
- Operator overloading (comparison)
- Operator overloading (addition)
- Method invocation
- Context manager support (with statement)

#### Object Initialization: __init__

constructor in Python is the __init__ :

```py
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []
```

This allows us to create new accounts like this:

```py
>>> acc = Account('bob')  # default amount = 0
>>> acc = Account('bob', 10)
```

#### Object Representation: __str__, __repr__

1. __repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.
2. __str__: The “informal” or nicely printable string representation of an object. This is for the enduser.

implement these two methods on the Account class:

```py
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)
```

```py
>>> str(acc)
'Account of bob with starting amount: 10'

>>> print(acc)
"Account of bob with starting amount: 10"

>>> repr(acc)
"Account('bob', 10)"
```

## Basic Statistics in Python — Probability

### probability

In a coin toss the only events that can happen are:

- Flipping a heads
- Flipping a tails

#### The data and the distribution

Intuitively, we’d like to use the scores of the wines to compare groups, but there comes a problem: the scores usually fall in a range.

Enter the **normal distribution**. The normal distribution refers to a particularly important phenomenon in the realm of probability and statistics.

In a probability context, the high point in a normal distribution represents the event with the highest probability of occurring.
As you get farther away from this event on either side, the probability drops rapidly, forming that familiar bell-shape.
The high point in a statistical context actually represents the mean.
 As in probability, as you get farther from the mean, you rapidly drop off in frequency.
That is to say, extremely `high` and `low` deviations from the `mean` are present but exceedingly rare.

If we visualize each group of scores as normal distributions, we can immediately tell if two distributions are different based on where they are.
We assume the scores will be normally distributed since we have a ton of data.