# 2.2. Function Practice

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

Hint: there's nothing stopping you from using a value multiple times.

```klipse
(defn square
  [x]
  (* _ _))

(= 9
   (square 3))
```

New concept: here we **def**ine a value outside our function definition.
We can still use that within our function, though.

```klipse
(def pi 3.14)

(defn circle-circumference
   [radius]
   (* 2 _ _))

(= 12.56
   (circle-circumference 2))
```

{{#include klipse-posttext.html}}
