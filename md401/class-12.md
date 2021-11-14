# Pandas

Panda is a game-changer for data science and analytics Pandas, more powerful than Excel and VBA. designed to make working with relational or labeled data both easy and intuitive Pandas uses fast, flexible, and expressive data structures .

```py
import pandas as pd
```

## facts about pandas

- A fast and efficient **DataFrame** object for data manipulation with integrated indexing;

- Tools for **reading and writing data** between in-memory data structures and different formats: CSV and text files, Microsoft Excel, SQL databases, and the fast HDF5 format;

- Intelligent **data alignment** and integrated handling of **missing data**: gain automatic label-based alignment in computations and easily manipulate messy data into an orderly form;

- Flexible **reshaping** and pivoting of data sets;

- Intelligent label-based **slicing, fancy indexing**, and **subsetting** of large data sets;

- Columns can be inserted and deleted from data structures for **size mutability**;

- Aggregating or transforming data with a powerful **group by** engine allowing split-apply-combine operations on data sets;

- High performance **merging and joining** of data sets;

- **Hierarchical axis indexing** provides an intuitive way of working with high-dimensional data in a lower-dimensional data structure;

- **Time series**-functionality: date range generation and frequency conversion, moving window statistics, date shifting and lagging. Even create domain-specific time offsets and join time series without losing data;

- Highly **optimized for performance**, with critical code paths written in Cython or C.

- Python with pandas is in use in a wide variety of **academic and commercial** domains, including Finance, Neuroscience, Economics, Statistics, Advertising, Web Analytics, and more.

**Vision**:

- Accessible to everyone
- Free for users to use and modify
- Flexible
- Powerful
- Easy to use
- Fast

## class pandas

Two-dimensional, size-mutable, potentially heterogeneous tabular data.

```py
class pandas.DataFrame(data=None, index=None, columns=None, dtype=None, copy=False)
```

Data structure also contains labeled axes (rows and columns).
Arithmetic operations align on both row and column labels. Can be thought of as a dict-like container for Series objects.

## Pandas Parameters

data and array (structured or homogeneous), Iterable, dict, or DataFrame
Dict can contain Series, arrays, constants, dataclass or list-like objects. If data is a dict, column order follows insertion-order.

Selecting a single column, which yields a Series, equivalent to df.A:

```py
df["A"]
```

- columnsIndex or array-like
Column labels to use for resulting frame. Will default to RangeIndex (0, 1, 2, …, n) if no column labels are provided.

- dtypedtype, default None
Data type to force. Only a single dtype is allowed. If None, infer.

- indexIndex or array-like
Index to use for resulting frame. Will default to RangeIndex if no indexing information part of input data and no index provided.

- Pandas is mainly used for data analysis.
Pandas allows importing data from various file formats such as comma-separated values, JSON, SQL, Microsoft Excel.[8] Pandas allows various data manipulation operations such as merging,[9] reshaping,[10] selecting,[11] as well as data cleaning, and data wrangling features

- copybool, default False
Copy data from inputs. Only affects DataFrame / 2d ndarray input.
