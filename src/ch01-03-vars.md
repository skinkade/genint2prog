# Variables

{{#include klipse-pretext.html}}

A variable is a piece of data we give a specific name to,
so we can easily use it from multiple places.
Variables are defined using the `def` operation,
where the first element following it is a *symbol*
representing the variable's name, and the following element is an *expression*
that represents the variable's value.
For instance, here we define a variable named 'message' the string value
"Hello, world!":

```klipse
(def message "Hello, world!")
```

We can also define a variable to be the result of an operation:

```klipse
(def four (+ 2 2))
four
```

You'll also notice two other interesting things with these snippets.
In the first, the editor printed `#'cljs.user/message`.
In the second, it printed the value of our variable `four`.

When you evaluate Clojure code within your editor, it automatically displays
the result. When we define a variable, the result is full name of the variable
(we'll get into more detail about that later).
When we evaluate a variable, we get its value.

{{#include klipse-posttext.html}}
