# Data

Clojure allows us to easily combine simple values
and simple data structures to create gradually more complex data.
I'll show an example of this, but don't worry if you don't understand
right away, because afterwards we'll go into more depth about
what each piece of data is and what it respresents.

Let's say you want to write a grocery list.
First, you need some way of representing text.
In Clojure, and most programming languages,
we surround a piece of text with double quotes:

```clojure
"apples"
```

Ah, but a grocery list has multiple items, of course.
We need a way of keeping multiple values together.
One way to do this in Clojure is by surrounding
multiple items with square brackets, like so:

```clojure
["apples", "bananas", "milk", "eggs", "bread"]
```

We need a way of saying *how many* of a thing we need.
This can be any old number like `6` or `42`.

Now to get a bit fancy.
When you shop in a supermarket, you generally shop one
area at a time, and grab the items in that area all at once,
instead of going back and forth through the store.
So, we want to group our grocery list into categories,
so our shopping can be more efficient:

```clojure
{"produce" ["apples", "bananas"],
 "dairy"   ["milk", "eggs"],
 "bakery"  ["bread"]}
```

Let's break that down a bit.
In each line, the first item is an area of the store,
and the second is a series of goods in that area we want to buy.

Let's go one step further, just for fun before we get into the boring bits.

For each item we're buying, we want to have alongside it the
number we're buying of it.

Just as we made a series of pairs above,
we could say that an item on our grocery list is also a
series of pairs:

```clojure
{"item"   "apple",
 "number" 10}
```

And if we combine that with our store area categorization,
we get something like:

```clojure
{"produce" [{"item"   "apple",
             "number" 10},
            {"item"   "banana",
             "number" 6}],
 "dairy"   [{"item"   "milk",
             "number" 1},
            {"item"   "eggs",
             "number" 12}],
 "bakery"  [{"item"   "bread",
             "number" 1}]}
```

## Data Types

Data can take the form of either single, individual values, or
structures which can contain more than one value.
Data can also be broken down into categories,
which are called `types`.
These types are related to how a piece of data is stored
in the computer's memory.
This section explains some of Clojure's core data types.

### Numbers

In computing, there is a distinction between whole numbers
and numbers with trailing decimal places.
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
characters have a backslash before them like `\c`.

### Truthiness

The technical term for a value that can be either true or false is a **boolean**.
These can often be thought of as the answers to yes-or-no questions.

Did I walk the dog this morning? Yes (true).


## Collections

There are a number of ways of storing a series of multiple values.
Two ways available to us in Clojure are **lists** and **vectors**,
which are both types of *collections*.

Side note: Clojure descends from a language called Lisp,
whose name comes from shortening "**lis**t **p**rocesser".

Lists can we written as a series of values surrounded by parentheses,
with or without commas, like:

```clojure
("apples" "eggs" "bread")
```

Lists are fast to add items to, but when you go to find an item,
you can only grab the *first* item,
followed by another list containers the *rest* of the items,
which makes them slower to go through.
If you want to reach the last item in a list 1,000 elements long,
you have to go through each of the 999 elements before it.

We'll go over why this is later on.

Vectors are written as a series of values surrounded by square brackets:

```clojure
["apples" "eggs" "bread"]
```

Each element in a vector has a numeric ID, called an index.
Indexes start at 0 and increment, so the first element is index 0,
the second is index 1, and so on.
If you know the index of an element, you can retrieve it instantly.
It is slower to add items to compared to a list, however.



### Pairs of Keys and Values

A structure known as a **hash map** or simply **map** is the
bread and butter of passing data around in Clojure.
It is another type of collection.
Think about ID numbers like on passports and drivers licenses.
With one value, a government system can look up data on a person.

Maps have *keys* which are pieces of data that serve as identifiers,
and matching *values*, which could be any type of data,
incuding other maps!

A map is written as a series pairs of a key followed by its value.
There is no separator between a key and its value besides a space,
and while you can optionally separate pairs by commas,
conventionally we put each pair on its own line.

A simple example:

```clojure
{"key1" "value1"
 "key2" "value2"}
```

Maps are often used for creating *lookup tables*.
A lookup table is a convenient way to translate some type of ID
to its value.

Below is a lookup table of month numbers to their shorthand names.

```clojure
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



### Sets

A set is another sort of collection, which is a sequence containing
only unique values.

Let's say you're hosting a party, and are making a guest list.
If someone repeatedly told you that they're coming,
you wouldn't add their name to the guest list multiple times.
In this case, you can use a set of guest names to make sure
that there's no duplicate entries.

```clojure
#{"Greg" "Charlie" "Taylor"}
```
