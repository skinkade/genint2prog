# 3.1 Variables

{{#include klipse-pretext.html}}

You saw in the final exercise of chapter two that, in addition to defining
our own functions, we can define *variables* as well.

Variables are pieces of data that we give a name to so we can easily
reference them from any number of places.

We **def**ine a variable with `def`:

```klipse
(def four 4)

four
```

In addition to using variables in our function definitions,
we can also use them when we're creating other variables.
Going back to the final exercise of chapter two,
here's an example:

```klipse
(def pi 3.14)

(def radius 2)

(def circumference (* 2 pi radius))

circumference
```

Take the last grocery list structure we made, for example.
We could define each of our categories of items as their
own variables, then include them within
the overall grocery list variable.

Try adding to the items we want to buy,
or maybe even add a section, if you're up to it!

```klipse
(def produce-items ["apples" "bananas"])
(def dairy-items ["milk" "eggs"])
(def bakery-items ["bread"])

(def grocery-list
  {"produce" produce-items,
   "dairy"   dairy-items,
   "bakery"  bakery-items})

grocery-list
```

Alternatively, given a complex piece of data,
we can grab smaller pieces of data out of it.
Let's say we're in the dairy section of the
store, so we want to find the list of items that
we want to grab in this section.
We can do this this by using the `get` function
on our grocery list with the name of the current section:

```klipse
(def grocery-list
  {"produce" ["apples", "bananas"],
   "dairy"   ["milk", "eggs"],
   "bakery"  ["bread"]})

(def current-section "dairy")

(def items-to-get
  (get grocery-list current-section))

items-to-get
```

Breaking that down: we have a piece of data which are names of grocery store
sections associated with items that we want to buy in that section.
We have given this data the name `grocery-list` by defining it as a variable.

We define another variable called `current-section` with the section
of the store we're currently in, `"dairy"`.

Then we `get`, from our grocery list, the items associated
with the current section we're in.

Try changing the value of `current-section` to `"produce"` or `"bakery`".
And again, if you're up to it, try adding a new section of your own!

{{#include klipse-posttext.html}}
