<!-- 
   So I know that a lot of programming books start with basic numeric stuff, 
   but I'm wondering if it might be better to start somewhere else here. 
   In the introduction, you talk about letters -> words -> sentences -> etc. 
   Perhaps that might be a good way to start here? Talking about making 
   strings and substrings or something? Idk, just a thought. Math is the "classic" 
   way to start, but I always worry in Lisps it'll be off-putting since 
   "that's not how you write math". 

   It's probably not the best way to go, but I don't know. Just a thought.
-->
# 2. Let the Code Begin

{{#include klipse-pretext.html}}

Let's start telling our computers what to do, shall we?
We'll start with the absolute basics: adding two numbers together.

```klipse
(+ 2 2)
```

Already a lot going on, but don't worry.

<!-- 
   I removed this because the learner doesn't really know what interactive 
   programming is or why that's exciting at this point. Comes a little out of nowhere?
-->
Firstly, we're already living up to the title of this book.
In the block above, you'll see two panes:
the top is editable code, and the bottom is the result. Here,
we can interactively write some code, and the result will appear to us instantly!

(That's nothing compared to what we'll be getting up to later, though 😉)

Second, that look awfully weird, doesn't it?
Why the parentheses, *and why does the plus sign come before the numbers?*

<!-- 
   Felt like this paragraph could use a rework. Hope you like the changes.
 -->
This is a peculiar feature of Clojure that might look a little odd at first glance!
Here's what's going on - Clojure is composed of what we call *expressions*.
*Expressions* are just anything that can be *evaluated* and in turn produce *values*. 
An expression can be as simple as the number `42` or the word `"apples"`, 
but they can also get more complicated, like a list of items. 
When an expression is a list of items, we group those items together inside 
parentheses - like in our list above `(+ 2 2)`. When our expression is a list of 
items like this, we call the first element the *function* and everything after 
it the *arguments* 
(or think about math class, where we called these the *operator* and *operands*).

<!-- Just changed this to reflect the slight change of language above -->
In this case the function is the plus sign, and it's an addition operator.
The numbers that follow are the operands, so we're adding those numbers.

You can write any number of numbers to be fed into this addition operator.
Unlike with typical math, you don't need to write a '+' between each number. 
This is really handy when trying to add just a bunch of numbers:

```klipse
(+ 1 2 3 4 5 6 7 8 9)
```

<!-- Upbeat tone -->
And subtraction, multiplication and division work the same way!
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
