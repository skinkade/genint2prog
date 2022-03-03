# Data Types

Data can take the form of either single, individual values, or
structures which can contain more than one value.

## Scalar values

The technical term for a piece of data that cannot be broken down any further
is a **scalar**.
We'll now go over the fundamental scalar types available to us in Clojure.

### Numbers

There are two important things to note about numbers in computing:
- there is a distinction between numbers with or without a decimal point
- the data types that hold numeric values have sizes, which determine how big a number they can represent *(is this relevant to a beginner?)*

We'll address these points in more detail later on.
For now, know that whole numbers without a decimal point are called **integers**,
such as `1`, `100`, or `9841098`; and numbers with decimal points are called **floats**,
such as `3.14` or `81.9841`.

### Text

A **character** is a single unit of text, such as a letter, a piece of punctuation,
a digit, or special character.

A sequence of characters to form a word, sentence, or longer, is called a
**string** (as in, the characters are strung together).

Characters and strings are typically surrounded by single and/or double quote characters,
depending on the language.
In Clojure, strings are surrounded by double quotes like `"Hello!"`, while
characters can be preceded by a backslash like `\c`.

### Truthiness

The technical term for a value that can be either true or false is a **boolean**.
These can often be thought of as the answers to yes-or-no questions.

Did I walk the dog this morning? Yes (true).


## Sequences

There are a number of ways of storing a series of multiple scalar values.
Two ways available to us in Clojure are **lists** and **vectors**.

Side note: Clojure descends from a language called Lisp,
whose name comes from shortening "**lis**t **p**rocesser".

We'll start with vectors, which are a series of values surrounded
by square brackets:

```
["hi" "hello" "yes" "indeed" "hm" "quite"]
```

Vectors and lists are numerically indexed, starting at 0.
In the vector above:
- index 0 is "hi"
- index 1 is "hello"
- and so on

**TODO**: explain indexing and add diagram

To write a list literal\*, you surround a series of values with parentheses,
with a single quote at the beginning:

```
'(1 2 3 4 5)
```

\* *literal* means the way of writing a constant value

We'll get to why that single quote is necessary when we cover syntax.

The basic difference between lists and vectors is:
- lists are fast to add items to, but slow to find a specific item
- vectors are slower to add items to than lists, but fast to find specific items

This book will largely be using vectors in its examples.



## Key-value pairs

A structure known as a **hash map** or simply **map** is the
bread and butter of passing data around in Clojure.
Think about IDs like on passports and drivers license.
With one value, a government system can look up data on a person.

Maps have *keys* which are values that serve as identifiers,
and a matching *value*, which could be any type of data,
incuding other maps!

A map is defined as series of keys followed immediatedly
by their value within curly brackets.
There is no separator between a key and its value besides a space,
and while you can optionally separate pairs by commas,
conventionally we put each pair on its own line.

A simple example:
```
{"key1" "value1"
 "key2" "value2"}
```

A lookup table\* of month number and their short month names:
```
{ 1 "Jan"
  2 "Feb"
  3 "Mar"
  4 "Apr"
  5 "May"
  6 "Jun"
  7 "Jul"
  8 "Aug"
  9 "Sep"
 10 "Oct"
 11 "Nov"
 12 "Dec"}
```

\* *lookup tables* are convenient ways of converting one value to another
