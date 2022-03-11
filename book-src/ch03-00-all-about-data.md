# 3. All About Data

Let's say we want to start writing a grocery list.
How do we do that: one item at a time.

We'll say for the moment that an item on our grocery list
is just the name of that item.
In most programming languages, pieces of text are written
surrounded by double quotes:

```clojure
"apples"
```

Ah, but a grocery list has multiple items, of course.
If we were to just write multiple pieces of text...

```clojure
"apples"
"bananas"
"milk"
```

... there's nothing actually tying those things together.
They need to be individual pieces within some larger whole -
a slightly more complex piece of data.
In Clojure, one way of doing this is to write the individual pieces
within square brackets, optionally with commas in between, like so:

```clojure
["apples", "bananas", "milk", "eggs", "bread"]
```

Let's go one step further.
What if we wanted to break our items into categories?
In most American grocery stores, apples and bananas with be in the produce section,
milk and eggs in the dairy section, and bread in the bakery.

