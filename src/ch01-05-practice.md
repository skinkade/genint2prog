# Data & Code Practice

{{#include klipse-pretext.html}}

We can check if two values are equal using the `=` operator.
These practice problems gradually get more difficult.

```klipse
(= 4
   (+ 2 2))
```

Modify the following code examples, replacing the underscores with values,
so the editor prints `true`.

```klipse
(= 10
   (+ 3 _))
```

<hr />

```klipse
(= 30
   (* 5 _))
```

<hr />

```klipse
(= _
   (/ 36 9))
```

<hr />

```klipse
(= _
   (+ (* 3 4)
      (/ 40 5)))
```

<hr />

```klipse
(defn times-five
  [x]
  (* 5 x))

(= _
   (+ (times-five 4)
      5))
```

<hr />

```klipse
(defn square
  [x]
  (* _ _))

(= 9
   (square 3))
```

<hr />

Challenge problem time!
Hint: you can reference a variable within a function, even if that variable
isn't part of the function's input.

```klipse
(def pi 3.14)

(defn circle-circumference
   [radius]
   (* _ _ _))

(= 12.56
   (circle-circumference 2))
```

{{#include klipse-posttext.html}}
