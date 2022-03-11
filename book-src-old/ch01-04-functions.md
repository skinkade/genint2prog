# Functions

{{#include klipse-pretext.html}}

We're far from limited to the operators provided to us by Clojure.
Let's define operations of our own called **functions**.
For our purposes, a function is a piece of code that takes some input
and returns some output.

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

## Functions as Data

And now for something magical: in Clojure, code...
is *also data!*
Fundamentally, we can also define a function using a regular `def`:

```klipse
(def add-ten
  (fn [x]
      (+ 10 x)))

(add-ten 5)
```

The form `(fn *args* *body*)` is known as an *anonymous function*
\- a function without a name we can call it by.
In the above code, we use `def` to give a name to function.
In reality, the `defn` operation is actually a *wrapper*\* around
`def` and `fn`, with some other features baked in that we'll get to later.

\* *wrappers* are pieces of code that combine some other components,
   usually in a simplified way

{{#include klipse-posttext.html}}
