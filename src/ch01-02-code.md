# Calling Code

{{#include klipse-pretext.html}}

Code, as mentioned, is a series of instructions for a computer to execute.
Let's start by adding two numbers together.

```klipse
(+ 2 2)
```

There's actually quite to show with this one line!
The code box you see above is interactive, and you're
free to modify its contents to see what you get.

Why does this code have parentheses around the plus sign and
two numbers? And why does the plus sign appear *before*
the two numbers?

Let's take a step back for a moment and discuss the syntax of
Clojure and the Lisp family. Lisps such as Clojure consist of
*expressions*, and an expression can be either a value, or a list
where the first element is an operation to be applied to the
other elements of the list.

In this case, we're performing an addition operation
(represented by the plus sign) on the numbers that follow.
This syntax, and how addition is implemented in Lisps,
allows us to add together however many numbers we want,
without having to write a plus sign between each one.

```klipse
(+ 1 2 3 4 5 6 7 8 9)
```

Subtraction, multiplication, and division also function the same way.

```klipse
(- 10 3 2)
```

<hr />

```klipse
(* 5 5)
```

<hr />

```klipse
(/ 50 5)
```

We can also chain series of expressions.
When we do this, we often *pretty-print* them by putting one expression on each
line to improve readability.

```klipse
(+ (- 10 3 2)
   (* 5 5)
   (/ 50 5))
```

{{#include klipse-posttext.html}}
