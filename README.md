# nlogo-utils

<!-- badges: start -->
[![Project Status: Active - The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
<!-- badges: end -->

## Overview

`nlogo-utils` is a repository that I (Daniel Vartanian) use to store and organize my [NetLogo](https://ccl.northwestern.edu/netlogo/) utility functions (i.e., `to` and `to-report` [procedures](https://ccl.northwestern.edu/netlogo/docs/programming.html#procedures)).

This is primarily intended for personal use, but you are welcome to use it if you find it helpful. Please note that not all functions are documented.

> If you find this project useful, please consider giving it a star! &nbsp; [![GitHub repo stars](https://img.shields.io/github/stars/danielvartan/nlogo-utils)](https://github.com/danielvartan/nlogo-utils)

## How to Use

All functions are located in the `nlogo` directory. Each function resides in its own file named after the function, except for test, check, and assertion functions, which are grouped by category (for example, `check-integer.nls` contains `is-integer?`, `test-integer`, `check-integer`, and `assert-integer`).

Some functions may require dependencies, such as NetLogo extensions or other functions. Any dependencies are listed in the file header.

Here are some examples:

### Control Flow and Logic

- `any-member?` (`to-report`): Tests if any element in a list is a member of another list
- `any-true?` (`to-report`): Tests if any element in a list is `true`
- `list-any?` (`to-report`): Tests if any element in a list is equal to a specified value or to values in another list
- `all-member?` (`to-report`): Tests if all elements in a list are members of another list
- `all-true?` (`to-report`): Tests if all elements in a list are `true`
- `list-all?` (`to-report`): Tests if all elements in a list are equal to a specified value or to values in another list

### Defensive Programming

These functions follow NetLogo naming conventions for testing, as well as the conventions used in the [`checkmate`](https://mllg.github.io/checkmate/) R package.

`test` functions return `true` or `false`. `check` functions return `true` if the test passes, or a string with an error message if it fails. `assert` functions are procedures (not reporters) that throw an error if the test fails.

- `is-atomic?` `test-atomic` (`to-report`): Tests whether a value is not a list
- `is-logical?` `test-logical` `test-boolean` (`to-report`): Tests whether a value is `true` or `false`
- `is-integer?` `test-integer` (`to-report`): Tests whether a value is an integer number
- `is-numeric?` `test-number` `test-numeric` (`to-report`): Tests whether a value is a number (integer or float)
- `is-string?` `test-string` (`to-report`): Tests whether a value is a string
- `is-list?` `test-list` (`to-report`): Tests whether a value is a list
- `is-true?` `test-true` (`to-report`): Tests whether a value is `true`
- `is-false?` `test-false` (`to-report`): Tests whether a value is `false`
- `dir-exists?` `test-dir-exists` (`to-report`): Tests whether a directory exists
- `test-file-exists` (`to-report`): Tests whether a file exists
- `is-gis?` `test-gis` (`to-report`): Tests whether a value is a [GIS dataset](https://ccl.northwestern.edu/netlogo/docs/gis.html#gis:type-of)
- `is-nan?` `test-nan` (`to-report`): Tests whether a value is `NaN` (not a number). This is useful when using the `gis` extension, as GIS datasets may contain `NaN` values.
- `is-between?` `test-between` (`to-report`): Tests whether a value is between two numbers
- `test-choice` (`to-report`): Tests whether a value is one of a set of choices
- `is-windows?` `test-windows` (`to-report`): Tests whether the user is running NetLogo on a Windows operating system

<br>

- `assert-atomic` (`to`): Asserts that a value is not a list
- `assert-logical` `assert-boolean` (`to`): Asserts that a value is `true` or `false`
- `assert-integer` (`to`): Asserts that a value is an integer
- `assert-number` `assert-numeric` (`to`): Asserts that a value is a number (integer or float)
- `assert-string` (`to`): Asserts that a value is a string
- `assert-list` (`to`): Asserts that a value is a list
- `assert-true` (`to`): Asserts that a value is `true`
- `assert-false` (`to`): Asserts that a value is `false`
- `assert-dir-exists` (`to`): Asserts that a directory exists
- `assert-file-exists` (`to`): Asserts that a file exists
- `assert-gis` (`to`): Asserts that a value is a [GIS dataset](https://ccl.northwestern.edu/netlogo/docs/gis.html#gis:type-of)
- `assert-between` (`to`): Asserts that a value is between two numbers
- `assert-choice` (`to`): Asserts that a value is one of a set of choices
- `assert-windows` (`to`): Asserts that the user is running NetLogo on a Windows operating system

Several other assertion functions are also available. Check the `nlogo` directory for more details.

### File System

- `basename` (`to-report`): Returns the base name of a file or directory (i.e., the last part of the path)
- `file-path` (`to-report`): Creates a file path from a directory and a file name
- `list-files-by-pattern` (`to-report`): Lists files in a directory that match a specified pattern
- `normalize-path` (`to-report`): Normalizes a file path making it compatible with the user operating system

### Lists

- `as-list` (`to-report`): Converts an atomic value to a list
- `collapse` (`to-report`): Collapses a list into a string using a separator (e.g., `[1 2 3 4]` → `"1, 2, 3, 4"`)
- `combine` (`to-report`): Combines two lists into a single list
- `list-to-c` (`to-report`): Converts a NetLogo list into a string formatted as an R `c()` expression, with elements separated by commas (e.g., `[1 2 3]` → `"c(1, 2, 3)"`)
- `match` (`to-report`): Returns the first element in a list that matches a specified value
- `unique-outliers` (`to-report`): Returns a sorted list of unique outlier values from a given list. Outliers are defined as values greater than the third quartile plus a specified multiple of the interquartile range (IQR), or less than the first quartile minus the same multiple of the IQR. Duplicate values are removed before identifying outliers.

### Mathematical

- `distance-between` (`to-report`): Returns the distance between two numbers
- `quartile` (`to-report`): Returns the quartiles (Q1,Q2, Q3, Q4), the quartile length, and the interquartile range (IQR) of a list of numbers
- `random-beta` (`to-report`): Returns a random number from a beta distribution with parameters `alpha` and `beta`
- `rescale` (`to-report`): Rescales a number from one range to another

### Strings

- `as-string` (`to-report`): Converts any value to a string
- `num-to-str-month` (`to-report`): Converts a numeric month value (`1` for January, `2` for February, etc.) to its corresponding string representation (e.g., `1` → `"January"`)
- `rep-collapse` (`to-report`): Repeats and collapses a value into a string.
- `single-quote` (`to-report`): Returns values with single quotes. It also works with lists.
- `str-detect` (`to-report`): Detecs the presence/absense of a match in a string using a regular expression. Returns `true` if the match is found, `false` otherwise.
- `str-extract` (`to-report`): Extracts a match from a string using a regular expression. Returns the first match found, or `"NA"` if no match is found.
- `str-extract-all` (`to-report`): Extracts all matches from a string using a regular expression. Returns a list of all matches found, with `"NA"` for any non-matching elements.
- `str-remove` (`to-report`): Removes a match from a string using a regular expression. Returns the string with the first match removed, or the original string if no match is found.
- `str-remove-all` (`to-report`): Removes all matches from a string using a regular expression. Returns the string with all matches removed, or the original string if no matches are found.
- `str-replace` (`to-report`): Replaces a match in a string using a regular expression. Returns the string with the first match replaced, or the original string if no match is found.
- `str-replace-all` (`to-report`): Replaces all matches in a string using a regular expression. Returns the string with all matches replaced, or the original string if no matches are found.
- `str-to-num-month` (`to-report`): Converts a string representing a month (e.g., `"January"`) to its corresponding numeric value (`1`  for January, `2` for February, etc.).
- `test-string-in-r` (`to-report`): Tests whether a string is a valid R string.

### World

- `check-world-bleed` (`to-report`): Checks a range of `pxcor` and `pycor` values to identify any lines of patches with a value of `0`, `NA`, or `NaN`. Returns a list containing two ordered lists: one with the `pxcor` values and one with the `pycor` values of patches that meet this condition. If no such patches are found, both lists are empty.
- `remove-world-bleed` (`to`): Checks for and removes world bleed patches—lines of patches at the edges of the world with values of `0`, `"NA"`, or `NaN`.
- `show-values` (`to`): A procedure for use with a `forever` button that displays patch values under the mouse cursor in the NetLogo view. Useful for interactively inspecting patch data during model runs.

## License

[![License: CC0-1.0](https://img.shields.io/badge/license-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

The content is licensed under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/), placing these materials in the public domain. You may freely copy, modify, distribute, and use this work, even for commercial purposes, without permission or attribution.
