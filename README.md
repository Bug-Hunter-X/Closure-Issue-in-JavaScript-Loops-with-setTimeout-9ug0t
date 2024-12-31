# Closure Issue in JavaScript Loops with setTimeout

This repository demonstrates a common closure-related bug in JavaScript when using `setTimeout` within a loop.  The issue arises because the `setTimeout` callback does not capture the value of `i` at the time of its creation, but rather captures a reference to the variable `i` itself. By the time `setTimeout` finally executes, the loop has already completed, and `i` holds its final value.

## Bug Description
The provided `bug.js` file contains a function `myFunction` that uses a `for` loop to schedule multiple `setTimeout` calls.  The expected behavior is to log the numbers 0 through 9 with a one-second delay between each. However, due to the closure issue, the actual output is 10 repeated ten times because the loop finishes before any of the timeouts are executed. 

## Solution
The `bugSolution.js` file provides a corrected version of the function using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, thus capturing the correct value of `i` for each `setTimeout` call.