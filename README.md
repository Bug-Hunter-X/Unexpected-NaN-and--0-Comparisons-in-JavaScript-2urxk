# Unexpected NaN and -0 Comparisons in JavaScript

This repository demonstrates a common pitfall in JavaScript's loose equality (==) operator when dealing with NaN (Not a Number) and -0 (negative zero).

## The Problem

JavaScript's loose comparison (==) does not follow standard mathematical equality.  Specifically:

* **NaN is never equal to itself:** `NaN == NaN` evaluates to `false`.
* **-0 is equal to 0:** `-0 == 0` evaluates to `true`.

This leads to potentially unexpected behavior if not handled carefully.

The `bug.js` file shows an example of this unexpected behavior.  The `foo` function intends to check for equality, but its results will be surprising for the cases involving NaN and -0.

## The Solution

The solution is to use the strict equality operator (===) and a dedicated check for NaN, using the `Number.isNaN()` function.  The `bugSolution.js` file provides a corrected version of the `foo` function.

## How to Run

1. Clone this repository.
2. Open `bug.js` and `bugSolution.js` in a JavaScript environment (browser console, Node.js, etc.).
3. Run the code to observe the differences in behavior between the original and corrected functions.

This simple example highlights the importance of carefully considering the nuances of JavaScript's equality operators and always preferring strict equality (===) when possible.