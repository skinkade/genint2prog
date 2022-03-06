# Editing & Development

Programmers rarely use basic text editors.
Instead, we use *integrated development environments* (IDEs),
full of tools and features that making programming easy and more productive.

Visual Studio Code has quickly become the most popular free IDE.
There are numerous plugins for VS Code that extend its functionality,
including *Calva* - the de facto Clojure plugin for this IDE.

The development setup that we'll be configuring in this book
consists of VS Code + the Calva plugin, and a few other components.



## Java

Let's take this moment to mention how Clojure actually runs.
Programming languages provide a human-readable way of providing
instructions to computers, and the code you write is *compiled*
down to a lower level of operations to eventually run on hardware.
Some languages compile directly to *machine code* for this purpose.

Clojure, however, targets *language platforms*, primarily the
**Java Virtual Machine** (JVM).
The JVM was originally written for the Java programming language
\- a language we'll be repeatedly referencing throughout this book.
Not only is the JVM a robust, high-performance platform for running software,
there's a huge number of Java software components
\- called *libraries* \- that Clojure
automatically gains access to by being on the JVM.

To be able to run Clojure and other JVM software, however,
we need to install Java and the JVM separately.



## Leiningen

When we develop software, we don't operate on just one file of code.
Our code is broken up into pieces across files and folders,
forming a *codebase* within a *project*.
We also don't write everything ourselves.
As mentioned, there are numerous pre-built software components freely
available to us, written in Clojure or Java, which we can
require and include as *dependencies*.

We therefore need a project build tool, to be able to
build our codebase as a single piece of software
(or even multiple components),
as well as to manage our dependencies.

The de facto tool for this in the Clojure space is *leiningen*,
which we will also install and be using in our examples.
