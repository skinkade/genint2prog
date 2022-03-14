# 4. Conditions

{{#include klipse-pretext.html}}

I want dessert.
If there's apple pie in the house, I'll eat some apple pie,
and if not, I'll have some ice cream.

Let's express that in code!

```clojure
(if have-apple-pie?
  (eat apple-pie)
  (eat ice-cream))
```

This is called *conditional logic*:
- if [condition]
- then [do something]
- else [do a different thing]

In Clojure, this is expressed with the following form:

```clojure
(if condition?
  ;; then
  (do-thing)
  ;; else
  (do-other-thing))
```

A bunch of things to cover here!

Additional new concept: those lines starting with `;;` are *comments*.
Comments are lines within code that are not evaluated.
They're a way of explaining code right next to the code itself.
Here I added two comments to make it clearer that the first
expression after the `condition?` is what happens if `condition?`
is *true*, else the second expression happens.

Side note: conditions like this in Clojure typically have a question
mark at the end to make it clear they're either true or false.

Let's introduce one more function that'll make things easier
for this section. The `println` function **print**s a value
to its own **l**i**n**e of text.

Let's combine a number of concepts we've learned so far:
we'll have two number variables, then check if those numbers
are equal. If they are, we'll print a success message,
and if not, a failure message.

```klipse
(def x 2)
(def y 3)

(if (= x y)
  (println "The values are equal :)")
  (println "The values are not equal :("))
```

Another common example is changing behavior based on whether
a number is above or below some threshold.

```klipse
(def apples-eaten 2)

(defn eat-another-apple
  []
  (println "Keeping the doctor away for another day!"))

(if (> apples-eaten 3)
  (println "You've eaten an unreasonable number of apples")
  (eat-another-apple))
```

Here we check if the number of apples eaten so far is more than three,
in which case we give the user an indication that maybe they should
cool it with apples for the day.
Otherwise, go ahead and eat another (if they want).

{{#include klipse-posttext.html}}
