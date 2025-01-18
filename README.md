# JavaScript NaN Handling Bug

This repository demonstrates a common JavaScript bug related to how loose comparison (`==`) interacts with `NaN` values.

## Description

The `foo` function is designed to handle `null` values gracefully by returning 0 if either input is `null`.  However, when either `a` or `b` is `NaN`, the function returns `NaN`, which might be unexpected if the goal was to return 0 for any invalid or missing input.

## Bug

The bug lies in the loose comparison used. `NaN` does not equal itself in a loose comparison (`NaN == NaN` evaluates to `false`).  Therefore, the `if` condition doesn't catch `NaN` values, leading to unexpected `NaN` outputs.

## Solution

The solution involves using strict equality (`===`) and explicitly checking for `isNaN()`.  This ensures the function handles `NaN` values as intended.