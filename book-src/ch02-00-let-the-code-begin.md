# 2. Let the Code Begin

{{#include klipse-pretext.html}}

Let's start telling our computers what to do, shall we?
We'll start with the absolute basics: adding two numbers together.

```klipse
(+ 2 2)
```

Already a lot going on, eh?

Firstly, we're already living up to the title of this book.
In the block above, you'll see two panes:
the top is editable code, and the bottom is the result.
*Interactive programming, woo!*

(That's nothing compared to what we'll be getting up to later, though.)

Second, that look awfully weird, doesn't it?
Why the parentheses, *and why does the plus sign come before the numbers?*

This is a particular feature of the family of languages that Clojure comes from.
Clojure is composed of *expressions*. When an expression is a list of items
surrounded by parentheses, the first item is treated as an *operator* to be
applied to whatever follows.

In this case, the plus sign is an addition operator.
The numbers that follow are what get fed into that addition.

You can write any number of numbers to be fed into this addition operator.
Unlike with typical math, you don't need to write a '+' between each number.

```klipse
(+ 1 2 3 4 5 6 7 8 9)
```

Subtraction, multiplication, and division work the same way.
In the following code blocks, try changing the numbers, and/or
adding some more numbers.

```klipse
(- 10 3)
```

<hr />

```klipse
(* 5 5)
```

<hr />

```klipse
(/ 50 5)
```

We can also combine the results of expressions easily:

```klipse
(+ 10 (* 5 5))
```

Here we add 10 to the result of multiplying five by five.
When we chain a number of expressions together, we often write each expression
on its own line, and indent each line to match up with its "level".
For instance:

```klipse
(+ 1
   (+ 2 2)
   (+ 3 3)
   (+ 4
      (+ 5 5)))
```

See how `1`, `(+ 2 2)`, `(+ 3 3)`, and the beginning of `(+ 4 ...` are on all the same "level"?

`(+ 5 5)` is *nested* within another expression, so we indent one "level" further.


{{#include klipse-posttext.html}}
