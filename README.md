# nlogo-utils

<!-- badges: start -->
[![Project Status: Active - The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
<!-- badges: end -->

## Overview

`nlogo-utils` is a repository that I (Daniel Vartanian) use to store and organize my [NetLogo](https://ccl.northwestern.edu/netlogo/) utility functions (i.e., `to` and `to-report` [procedures](https://ccl.northwestern.edu/netlogo/docs/programming.html#procedures)).

This is primarily intended for personal use, but you are welcome to use it if you find it helpful. Please note that not all functions are documented.

> If you find this project useful, please consider giving it a star! &nbsp; [![GitHub repo stars](https://img.shields.io/github/stars/sustentarea/foodclim)](https://github.com/sustentarea/nlogo-utils/)

## How to Use

All functions are located in the `nlogo` directory. Each function resides in its own file named after the function, except for test, check, and assertion functions, which are grouped by category (for example, `check-integer.nls` contains `is-integer?`, `test-integer`, `check-integer`, and `assert-integer`).

Some functions may require dependencies, such as NetLogo extensions or other functions. Any dependencies are listed in the file header.

Here are a few examples:
> **Note:** In NetLogo, `atomic` values are any value that are not a list—such as numbers, strings, or booleans.

### Defensive Programming

These functions follow NetLogo naming conventions for testing, as well as the conventions used in the [`checkmate`](https://mllg.github.io/checkmate/) R package.

`test` functions return `true` or `false`. `check` functions return `true` if the test passes, or a string with an error message if it fails. `assert` functions are procedures (not reporters) that throw an error if the test fails.

- `is-atomic?` `test-atomic` (`to-report`): Tests whether a value is not a list.
- `is-logical?` `test-logical` `test-boolean` (`to-report`): Tests whether a value is `true` or `false`.
- `is-integer?` `test-integer` (`to-report`): Tests whether a value is an integer number.
- `is-numeric?` `test-number` `test-numeric` (`to-report`): Tests whether a value is a number (integer or float).
- `is-string?` `test-string` (`to-report`): Tests whether a value is a string.
- `is-list?` `test-list` (`to-report`): Tests whether a value is a list.
- `is-true?` `test-true` (`to-report`): Tests whether a value is `true`.
- `is-false?` `test-false` (`to-report`): Tests whether a value is `false`.
- `dir-exists?` `test-dir-exists` (`to-report`): Tests whether a directory exists.
- `test-file-exists` (`to-report`): Tests whether a file exists.
- `is-gis?` `test-gis` (`to-report`): Tests whether a value is a [GIS dataset](https://ccl.northwestern.edu/netlogo/docs/gis.html#gis:type-of).
- `is-between?` `test-between` (`to-report`): Tests whether a value is between two numbers.
- `test-choice` (`to-report`): Tests whether a value is one of a set of choices.

<br>

- `assert-atomic` (`to`): Asserts that a value is not a list.
- `assert-logical` `assert-boolean` (`to`): Asserts that a value is `true` or `false`.
- `assert-integer` (`to`): Asserts that a value is an integer.
- `assert-number` `assert-numeric` (`to`): Asserts that a value is a number (integer or float).
- `assert-string` (`to`): Asserts that a value is a string.
- `assert-list` (`to`): Asserts that a value is a list.
- `assert-true` (`to`): Asserts that a value is `true`.
- `assert-false` (`to`): Asserts that a value is `false`.
- `assert-dir-exists` (`to`): Asserts that a directory exists.
- `assert-file-exists` (`to`): Asserts that a file exists.
- `assert-gis` (`to`): Asserts that a value is a [GIS dataset](https://ccl.northwestern.edu/netlogo/docs/gis.html#gis:type-of).
- `assert-between` (`to`): Asserts that a value is between two numbers.
- `assert-choice` (`to`): Asserts that a value is one of a set of choices.

### Control Flow

- `any-true?` (`to-report`): Tests if any element in a list is `true`.
- `all-true?` (`to-report`): Tests if all elements in a list are `true`.

### Other Functions

- `as-list` (`to-report`): Converts an atomic value to a list.
- `as-string` (`to-report`): Converts any value to a string.
- `combine` (`to-report`): Combines two lists into a single list.
- `distance-between` (`to-report`): Returns the distance between two numbers.
- `file-path` (`to-report`): Creates a file path from a directory and a file name.
- `list-to-c` (`to-report`): Converts a NetLogo list into a string formatted as an R `c()` expression, with elements separated by commas (e.g., `[1 2 3]` → `"c(1, 2, 3)"`).
- `match` (`to-report`): Returns the first element in a list that matches a specified value.
- `random-beta` (`to-report`): Returns a random number from a beta distribution with parameters `alpha` and `beta`.
- `rep` (`to-report`): Returns a list with an atomic value repeated a specified number of times.
- `rescale` (`to-report`): Rescales a number from one range to another.
- `single-quote` (`to-report`): Returns values with single quotes. It also works with lists.
- `show-values` (`to`): A procedure for use with a `forever` button that displays patch values under the mouse cursor in the NetLogo view. Useful for interactively inspecting patch data during model runs.

## License

[![License: CC0-1.0](https://img.shields.io/badge/license-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

The content is licensed under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/), placing these materials in the public domain. You may freely copy, modify, distribute, and use this work, even for commercial purposes, without permission or attribution.
