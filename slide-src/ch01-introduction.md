---
marp: true
theme: default
paginate: true
---

<style>
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}

h1, h2, h3, h4, h5 {
    text-align: center;
}
</style>

<br>
<br>

# A Gentle Introduction to Interactive Programming

![width:300px center](img/clojure_logo.png)



---

## Goals

Plain English explanations of core programming concepts:

- basic data types
- variables and definitions
- functions
- conditions

---

## Clojure

- high-level programming language
  - lots of helpful features
- both fun and productive
- really good for processing data
- ***interactive***
  - instant feedback when you write code

---

## Data

- Any piece of digital information
  - Spreadsheet
  - Digital photo
  - MP3 music file
  - Plain text file

---

## Code

- Instructions executed by a computer
  - Tax calculations on spreadsheet
  - Apply filter or effect to photo
  - Boost bass of MP3
  - Spell check text file

---

## Data Types

- Categories of data
- Related to how data is stored in computer memory
- Related to what operations you can perform on a piece of data
  - Doing math calculations on numbers

---

## Data Types: Numbers

**Integers** - whole numbers, no decimal point

```clojure
100
-999
```

**Floats** - numbers with decimal points

```clojure
3.14
-100.0
```

---

## Data Types: Text

**Character** - letter, digit, punctuation, special character, etc

```clojure
\h \e \l \l \o \!
```

**String** - characters strung together as single piece of text

```clojure
"hello!"
```

---

## Data Types: Truth

**Boolean** - value representing either *true* or *false*

Has the dog been walked today? *true* (yes)
Is an elephant small? *false* (no)

---

## Data Types: Collections

Ways of storing multiple pieces of data together

Let's say you're building a grocery list...

---

## Data Types: Collections - Lists

- Clojure is a Lisp
  - Lisp stands for **lis**t **p**rocessor

```clojure
'("apples" "eggs" "milk")
```

Single quote explained later

Lists are fast to add items to, but slow to find individual items

---

## Data Types: Collections - Vectors

```clojure
["apples" "eggs" "bread"]
```

Vectors are slower to add items to, but fast to find items

Each item in a vector has a numeric ID, called an index, starting at 0

---

## Data Types: Collections - Maps

- Super useful!
- Pairs of *keys* and their matching *values*
- Think of the number on an ID card
  - computer system can look up details using that ID number
- Values can be any piece of data, including other maps!

```clojure
{"key1" "value1"
 "key2" "value2"}
```

---

## Data Types: Collections - Maps (cont.)

Maps are good for making *lookup tables*, which are used to convert some value to another. This matches month numbers to their names:

```clojure
{ 1 "Jan"
  2 "Feb"
  3 "Mar"
  4 "Apr"
  5 "May"
  6 "Jun"
  7 "Jul"
  8 "Aug"
  9 "Sep"
 10 "Oct"
 11 "Nov"
 12 "Dec"}
```

---

## Data Types: Collections - Sets

- Sequence of unique values
- If you're making a guest list to a party, and someone repeatedly says they're coming, you don't add their name to the guest list multiple times

```clojure
#{"Greg" "Charlie" "Taylor"}
```

---

## Calling Code

```clojure
(+ 2 2)
;; => 4
```

- Expression wrapped in parentheses (a list)
- First element is some operation
- Operation is applied to the following elements
- `+` is an addition operation, which is applied to everything after it, producing a sum

```clojure
(+ 1 2 3 4 5 6 7 8 9)
;; => 45
```

---

## Calling Code (cont.)

```clojure
(- 10 3 2)
;; => 5

(* 5 5)
;; => 25

(/ 50 5)
;; => 10
```

---

## Calling Code (cont.)

When putting a series of expressions together, we
*pretty-print* them by putting one on each line, and indenting them to match up.

```clojure
(+ (- 10 3 2)
   (* 5 5)
   (/ 50 5))
;; => 40
```

---

## Variables

- Piece of data we give name to
- We **def**ine a variable by giving a name (a symbol) to a value
- Value be any piece of data, including the result of an expression

```clojure
(def message "Hello!")

(def four (+ 2 2))

(def six (+ 2 four))
```

---

## Functions

- Type of operation
- For our purposes, take some input, return some output
- **de**fine a **f**u**n**ction with `defn` operation
- When we define a function, its inputs are called *parameters*
- When we call a function, its inputs are called *arguments*

```clojure
(defn add-ten
  [x]
  (+ 10 x))

(add-ten 5)
;; => 15
```

---

## Functions as Data

- `defn` is a combination of `def` and `fn`
- we could have written `add-ten` as:

```clojure
(def add-ten
  (fn [x]
      (+ 10 x)))
```

The form `(fn args body)` is known as an *anonymous function* - a function without a name we can call it by
