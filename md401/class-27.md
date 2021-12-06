# Django Models

![Django Models](assets/DjangoModels.jpg)

## Using models

Django handles all the dirty work of communicating with the database for you.

### Designing the LocalLibrary models

When designing your models it makes sense to have separate models for every "object" (a group of related information). In this case, the obvious objects are books, book instances, and authors.

Django allows you to define relationships that are one to one (OneToOneField), one to many (ForeignKey) and many to many (ManyToManyField).

The diagram also shows the relationships between the models, including their multiplicities. The multiplicities are the numbers on the diagram showing the numbers (maximum and minimum) of each model that may be present in the relationship.

eg: the connecting line between the boxes shows that Book and a Genre are related. The numbers close to the Genre model show that a book must have one or more Genres (as many as you like), while the numbers on the other end of the line next to the Book model show that a Genre can have zero or many associated books.

## Model primer

### Model definition

models.py file. They are implemented as subclasses of `django.db.models.Model`, and can include fields, methods and metadata. The code fragment below shows a "typical" model, named MyModelName:

```py
from django.db import models

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name
```

In the below sections we'll explore each of the features inside the model in detail:

**Fields**:

```py
my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
```

Note that when the label is used as a form label through Django frame, the first letter of the label is capitalised (for example my_field_name would be My field name).

**Metadata**:

```py
class Meta:
    ordering = ['-my_field_name']
```

example: if we chose to sort books like this by default:

```py
ordering = ['title', '-pubdate']
```

## Model management

- Managing model basically includes, updating, or deleting records, and running select queries.

### Creating and modifying records

- Create a new record using the model's constructor.

```py
    record = MyModelName(my_field_name="Instance #1")

```

- Save the object into the database.

```py
    record.save()
```

### Searching for records

- search is done using attributes of the object
- _Getting All Records_
  - QuerySet --> objects.all()
- _Getting Specific Records Based on a Criteria_
  - QuerySet --> filter()

### Defining the LocalLibrary Models

> from django.db import models
> from django.urls import reverse
> import uuid
