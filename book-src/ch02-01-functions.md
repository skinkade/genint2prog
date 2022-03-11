# 2.1. Functions

{{#include klipse-pretext.html}}

We've seen operators for addition, subtraction, multiplication, and division.
We're far from limited to those, though.
Clojure has hundreds of operators built-in.
Let's talk about how a lot of those operators are defined.

For the moment, we're going to say that a **function** is an operation
which takes some input data and returns some output data.

To **de**fine a **f**u**n**ction, we use the `defn` operator.
The form for this looks like:

```clojure
(defn function-name
    [input]
    (do-something-with input))
```

Remember that this is a list, where the first item is the operator `defn`.
In this case:
- the second item is the name we want to give to the function we're defining
- the third item specifies what inputs (in square brackets) we want this function to work with
- the fourth item is an expression for what we're going to do with our input

For example:

```klipse
(defn add-ten
  [x]
  (+ 10 x))

(add-ten 5)
```

Let's take a step back and break down exactly what we just did:
- we are defining a function named `add-ten`
- this function takes one input, which we call `x`
- we add 10 to whatever the value of `x` is

In the following code block, try writing completing this function
that multiplies a value by five:

```klipse
(defn times-five
  []
  ())

(times-five 4)
```

{{#include klipse-posttext.html}}
