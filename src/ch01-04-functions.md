# Functions

{{#include klipse-pretext.html}}

We're far from limited from the operators provided to us by Clojure.
Let's define operations of our own called **functions**.

We can define a function with `defn`, followed a symbol for its name,
and a vector of symbols for its input.
When we define a function, any inputs defined are referred to as *parameters*.
When we evaluate a function, any inputs we pass in are referred to as *arguments*.

Here we define a function named `add-ten` which takes an input parameter `x`.
We then evaluate that function, passing in `5` as the argument.
You'll see that `x`, within the *body* of the function, takes the place of the
value we pass in.

```klipse
(defn add-ten
  [x]
  (+ 10 x))

(add-ten 5)
```

{{#include klipse-posttext.html}}
