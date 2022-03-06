# Lists & Vectors

{{#include klipse-pretext.html}}

## Finding Elements

Clojure has convenience functions such as `first` and `second`
to retrieve items from a collection:

```klipse
(second [1 2 3])
```

More generally however, specific items can be retrieved using
the `nth` function (as in: 1st, 2nd, 3rd ... *nth*).
It has the form:

```
(nth collection index)
```

Remember that indexes start at 0, not 1, so if we want to grab
the 3rd element, we need to retrieve index 2:

```klipse
(nth [1 2 3] 2)
```

`nth` will throw an error if you try to retrieve an index that doesn't exist:

```klipse
(nth [1 2 3] 10)
```

There's also the `get` function, which in this instance functions
similarly to `nth`, but does not throw an error, instead returning `nil`.

```klipse
(get [1 2 3] 10)
```

Now is a good time to introduce the concept of *null values*,
called *nils* in Clojure. As opposed to the number 0 representing
zero of *something*, a *null* is the complete absence of a value.



## Adding Elements

To add an element to a list or vectors, we **conj**oin the
element to the collection with the `conj` function.
An interesting note: when we add an element to a vector,
it's added to the end.
When we add an element to a list, it's added to the beginning.

```klipse
(conj [1 2 3] 4)
```

```klipse
(conj '(1 2 3) 4)
```

To combine two lists or vectors into one, we **concat**enate them
with the `concat` function.

```klipse
(concat [1 2] [3 4])
```



## Generating

Let's create some data of our own, shall we?
Suppose we want to create a list of numbers from 1 to 10.
Clojure has a very useful function called `range`,
which has the form:

```
(range start end)
```

Let's see what we get...

```klipse
(range 1 10)
```

Ah, almost! One gotcha here is that the end of the range is *exclusive*,
that is, it excludes the number itself.
This means that the end of our range actually has to be one higher
than the end number we want:

```klipse
(range 1 11)
```

What if we want a list of 10 fives?
Clojure has the `repeat` function for that:

```
(repeat count value)
```

```klipse
(repeat 10 5)
```

### Infinite Lists

Through Clojure, we can harness the power of infinity!... in a way.
Clojure has many list functions which generate *infinite sequences*
that you can `take` however many items you want from.
The `take` function has the form:

```
(take count collection)
```

These infinite sequences don't actually generate their values all at once.
Doing so would cause a computer to run out of memory.
These sequences are *lazy* - they only generate values when those
values are requested.

`repeat` actually has a different form without a parameter
to specify a count of items to return:

```
(repeat value)
```

In this instance, it will return an infinite sequences of value.
If you were to evaluate this by itself in your REPL, it would print
a huge number of values and cause issues with your editor.

To get a list of 10 fives, we could have also written:

```klipse
(take 10 (repeat 5))
```

Important note: here you can see that we can pass the result of evaluating
a function as the argument of another function.


## Manipulation & Functions as Arguments

Functions in Clojure are *first-class*,
meaning they can be treated just like pieces of data.
*This includes being passed as arguments to other functions!*

Many core functions in Clojure take other functions as their arguments.
Often, these argument functions are used by calling function to somehow
manipulate a collection of data.

Before we discuss one such function, I'd like to get a potential source of
confusion out of the way. Clojure has data structures called *(hash) maps*,
and it also has a function called `map`, which are different things.

The `map` function has the form:

```
(map function collection)
```

It takes a function as its first input argument, which will be applied to each element
of its second input argument, a collection of data.
You can think of this as *mapping over* the data with some operation.

Let's take for an example the helper function `inc`.
Its name is short for *increment*, as in, adding 1 to a value.
When use `map` to apply `inc` to each value in a collection, we get...

```klipse
(map inc [1 2 3 4])
```

We showed in [chapter 1.4](ch01-04-functions.md) how to define
our own functions, both named and anonymous.

Let's pass in a custom function into `map`:

```klipse
(defn times-ten
  [x]
  (* 10 x))

(map times-ten [1 2 3 4])
```

But remember, a function doesn't need to have a name.
Instead of pre-defining a named function, we can also give `map`
an anonymous function in-place using `fn`:

```klipse
(map (fn [x] (* 10 x))
     [1 2 3 4])
```



### Generation Follow-up

Earlier, to generate a list of 1 through 10, we could have also generated an
infinite list with the function `iterate`:

```
(iterate function value)
```

Given a starting value `x` and a function `f`, it will return an infinite
sequence of `x`, `(f x)`, `(f (f x))`, and so on.

If we pick a starting value of 1, and use the funtion `inc` to increment
each item in the sequence, we should get 1, 2, 3, and so on.
Then we just need to `take` 10 items from the sequence.

```klipse
(take 10 (iterate inc 1))
```


## Printing Each Item

What if you want to do something to each item in a collection,
but you don't care what the result is?
Say for instance that you just want to display each value.

First you'll need to know the function `println`, which takes
one or more pieces of data, and prints a line in a console
containing the *human-readable* version of that data.

We can combine that with the function `doseq`, which **do**es something
to each item in a **seq**uence:

```klipse
(doseq [item [1 2 3 4]]
  (println item))
```

A lot going on there in just two lines!
Something brand new is the first argument, `[item [1 2 3 4]]`.
`doseq` uses this form to *bind* each value in `[1 2 3 4]` to
the variable `item`.
Then for each of these items, it evaluates `(println items)`.

You'll also notice that the editor printed `nil` at the end.
In Clojure, every evaluation has to return *something*,
and if it doesn't return something, it will default to returning `nil`.



## A Challenge

If you're ready, the following is a challenge that combines everything
we've learned so far, and introduce several more things.

Let's say we want display the following:

```
*
**
***
****
*****
```

What may seem simple is actually a bit tricky.
What is it that we need to do here?

Here's what we'll do:

- write a function that adds a '*' character to a string,
  in order to "grow" a string of stars
- generate a sequence of "growing" star strings
- take elements from this sequence
- print each element

Are you ready? Let's begin.

First, we need a function to "grow" our star strings.
We can use the function `str`, short for string, which takes
any number of arguments and combines them together into a single string.

```klipse
(str "a" 1 "b" 2)
```

```klipse
(defn add-star
  [s]
  (str s "*"))

(add-star "*")
```

Hey, two stars!

Now we need to generate a growing sequence.
We can use `iterate`, passing in our `add-star` function, with `"*"`
as the starting value.
Let's save this sequence to a variable called `stars`.

Remember, this sequence in infinite, so we need to `take` a number
of items in order for this to display without issue in our editor.

```klipse
(defn add-star
  [s]
  (str s "*"))

(def stars
  (iterate add-star "*"))

(def five-stars
  (take 5 stars))

five-stars
```

We're almost there!
We just need to print each item as a line with `doseq` and `println`.

```klipse
(defn add-star
  [s]
  (str s "*"))

(def stars
  (iterate add-star "*"))

(def five-stars
  (take 5 stars))

(doseq [star-line five-stars]
  (println star-line))
```

{{#include klipse-posttext.html}}
