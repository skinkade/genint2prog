# 3.1 Variables

{{#include klipse-pretext.html}}

You saw in the final exercise of chapter two that, in addition to defining
our own functions, we can define *variables* as well.

Variables are pieces of data that we give a name to so we can easily
reference them from any number of places.

We **def**ine a variable with the `def` operator:

```klipse
(def four 4)

four
```

In addition to using variables in functions,
we can also use them in the definitions of other variables.
Take the last grocery list structure we made, for example.
We could define each of our categories of items as their
own variables, then include them within
the overall grocery list variable.

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

Going back to the final exercise of chapter two,
here's another example:

```klipse
(def pi 3.14)

(def radius 2)

(def circumference (* 2 pi radius))

circumference
```

Again, feel free to modify the code above and play around!

{{#include klipse-posttext.html}}
