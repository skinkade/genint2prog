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

<!-- For some reason I found this wording a little confusing -->
In addition to using variables in our function definitions,
we can also use them when we're creating other variables.
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

<!-- 
  Maybe close this off with some interactive section that ends in something like...? 

  (def produce-items [... _])
  (def dairy-items [... _])
  (def bakery-items [... _])
  
  (def grocery-list 
    {"produce" _
     "dairy" _
     "bakery" _ })
  
  (= grocery-list 
     {"produce" [a b c]
      "dairy" [x y z]
      "bakery" [1 2 3]})
  
  I feel like this could use some example that they need to fill things in over 
  multiple expressions.
-->
Again, feel free to modify the code above and play around!

{{#include klipse-posttext.html}}
