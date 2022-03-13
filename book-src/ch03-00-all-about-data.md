# 3. All About Data

{{#include klipse-pretext.html}}

Let's say we want to start writing a grocery list.
How do we do that?: one item at a time.

We'll say for the moment that an item on our grocery list
is just the name of that item, to keep it simple.
In most programming languages, pieces of text are written
surrounded by double quotes:

<!-- I like this approach of first saying the ways we *don't* represent something -->
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

I suppose we could also write them as a single piece of text...

```clojure
"apples, bananas, milk"
```

... but that'd quickly get a bit messy when we have 20+ items,
and especially when we need to sort them or perform some
other operations.

<!-- Optionality of commas is an implementation detail that isn't important to know yet -->
They need to be individual pieces within some larger whole -
a slightly more complex piece of data.
In Clojure, one way of doing this is to write the individual pieces
within square brackets, like so:

```clojure
["apples", "bananas", "milk", "eggs", "bread"]
```

Much better! This particular piece of data is one we can easily
perform useful operations on, such as sorting the items alphabetically:

```klipse
(sort ["apples", "bananas", "milk", "eggs", "bread"])
```

We can easily, say, grab the first or last item of the grocery list:

```klipse
(first ["apples", "bananas", "milk", "eggs", "bread"])
```

<hr />

```klipse
(last ["apples", "bananas", "milk", "eggs", "bread"])
```

Here we've introduced the functions `sort`, `first`, and `last` -
all handy functions for working with series of data.
Here's one more: if we want to add a new item to our grocery list,
we **conj**oin an item to it with the `conj` function:

```klipse
(conj ["apples", "bananas", "milk", "eggs", "bread"] "juice")
```

<!-- 
    I'd have an interactive section before getting them to start with maps.
-->

Let's go one step further.
In most American grocery stores, apples and bananas with be in the produce section,
milk and eggs in the dairy section, and bread in the bakery.

To say that bread is in the bakery, we might create a mapping of the name
of an item to the area of the store it's found in.
We might write that map something like:

```clojure
{"bread" "bakery"}
```

Within those curly brackets is a pair of two pieces of text.
What we're saying with this data is that first value
is associated with the second value.

For a grocery list, we probably want to flip this the other way around.
When we shop at the store, we'll go to a section, and pick up everything
we need in that section at once, so we don't bounce all over the store.

In that case, for each section of the store, we want that section to be
associated with a smaller series of relevant items.
In Clojure, we would write that something like this:

```clojure
{"produce" ["apples", "bananas"],
 "dairy"   ["milk", "eggs"],
 "bakery"  ["bread"]}
```

Now you can see that we've combined three different types of data -
pieces of text, series of items, and association of items -
into a very useful structure.

{{#include klipse-posttext.html}}
